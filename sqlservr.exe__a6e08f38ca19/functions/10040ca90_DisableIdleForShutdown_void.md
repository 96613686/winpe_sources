# DisableIdleForShutdown(void)

- ea: `0x10040ca90`
- end: `0x10040cbce`
- name: `?DisableIdleForShutdown@@YAXXZ`
- size: `318`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x10040c5b0`
- `0x100418d20`

## callees

- `0x100409530`
- `0x100409760`
- `0x10040abb0`
- `0x10040ad90`
- `0x10040ca90`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x10040cb43`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x10040cb43`
- `sqldk!?sm_isIdleDetectionEnabled@SOS_PublicGlobals@@2HA` at `0x10040caa4`
- `sqldk!?sm_isIdleDetectionEnabled@SOS_PublicGlobals@@2HA` at `0x10040cb30`
- `sqldk!?sm_isIdleDetectionEnabled@SOS_PublicGlobals@@2HA` at `0x10040cbb0`
- `sqldk!?WakeUpSuspendedNodes@ResourceMonitor@@SAXHW4WakeUpReason@@@Z` at `0x10040cb63`
- `sqldk!?WakeUpSuspendedNodes@ResourceMonitor@@SAXHW4WakeUpReason@@@Z` at `0x10040cbaa`
- `sqldk!?WakeUpSuspendedNodes@ResourceMonitor@@SAXHW4WakeUpReason@@@Z` at `0x10040cb63`
- `sqldk!?WakeUpSuspendedNodes@ResourceMonitor@@SAXHW4WakeUpReason@@@Z` at `0x10040cbaa`
- `sqldk!?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A` at `0x10040cab4`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=5
void DisableIdleForShutdown(void)
{
  struct SOS_Node *i; // rbx
  int v1; // eax
  _QWORD v2[4]; // [rsp+28h] [rbp-30h] BYREF
  int v3; // [rsp+48h] [rbp-10h]

  if ( SOS_PublicGlobals::sm_isIdleDetectionEnabled )
  {
    v2[3] = 0;
    v3 = 0;
    v2[2] = SOS_PublicGlobals::sm_NodeManager[0];
    v2[0] = TList<NodeManager,SOS_Node,16,TListSLock>::GetHead(SOS_PublicGlobals::sm_NodeManager[0]);
    v2[1] = TList<NodeManager,SOS_Node,16,TListSLock>::GetTail(SOS_PublicGlobals::sm_NodeManager[0]);
    for ( i = SOS_NodeEnumIncludeUninitializedNodes::GetNext((SOS_NodeEnumIncludeUninitializedNodes *)v2, 0);
          i;
          i = SOS_NodeEnumIncludeUninitializedNodes::GetNext((SOS_NodeEnumIncludeUninitializedNodes *)v2, i) )
    {
      if ( (*((_BYTE *)i + 1568) & 0x10) == 0 )
        break;
    }
    while ( i )
    {
      if ( SOS_PublicGlobals::sm_isIdleDetectionEnabled )
      {
        GetSystemTimeAsFileTime((LPFILETIME)i + 241);
        v1 = *((_DWORD *)i + 68);
        if ( v1 )
        {
          *((_DWORD *)i + 68) = 0;
          ResourceMonitor::WakeUpSuspendedNodes(v1 == 2, 0);
        }
      }
      for ( i = SOS_NodeEnumIncludeUninitializedNodes::GetNext((SOS_NodeEnumIncludeUninitializedNodes *)v2, i);
            i;
            i = SOS_NodeEnumIncludeUninitializedNodes::GetNext((SOS_NodeEnumIncludeUninitializedNodes *)v2, i) )
      {
        if ( (*((_BYTE *)i + 1568) & 0x10) == 0 )
          break;
      }
    }
    ResourceMonitor::WakeUpSuspendedNodes(0, 3);
    SOS_PublicGlobals::sm_isIdleDetectionEnabled = 0;
    SOS_NodeEnumIncludeUninitializedNodes::~SOS_NodeEnumIncludeUninitializedNodes((SOS_NodeEnumIncludeUninitializedNodes *)v2);
  }
}

```

## disassembly

```asm
0x10040ca90  push    rdi
0x10040ca92  sub     rsp, 50h
0x10040ca96  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x10040ca9f  mov     [rsp+58h+arg_0], rbx
0x10040caa4  mov     rax, cs:__imp_?sm_isIdleDetectionEnabled@SOS_PublicGlobals@@2HA; int SOS_PublicGlobals::sm_isIdleDetectionEnabled
0x10040caab  cmp     dword ptr [rax], 0
0x10040caae  jz      loc_10040CBC3
0x10040cab4  mov     rbx, cs:__imp_?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A; NodeManager SOS_PublicGlobals::sm_NodeManager
0x10040cabb  xorps   xmm0, xmm0
0x10040cabe  movdqu  [rsp+58h+var_30], xmm0
0x10040cac4  xor     edi, edi
0x10040cac6  mov     [rsp+58h+var_18], rdi
0x10040cacb  mov     [rsp+58h+var_10], edi
0x10040cacf  mov     [rsp+58h+var_20], rdi
0x10040cad4  mov     [rsp+58h+var_20], rbx
0x10040cad9  mov     rcx, rbx
0x10040cadc  call    ?GetHead@?$TList@VNodeManager@@VSOS_Node@@$0BA@UTListSLock@@@@QEAAPEAVSOS_Node@@XZ; TList<NodeManager,SOS_Node,16,TListSLock>::GetHead(void)
0x10040cae1  mov     qword ptr [rsp+58h+var_30], rax
0x10040cae6  mov     rcx, rbx
0x10040cae9  call    ?GetTail@?$TList@VNodeManager@@VSOS_Node@@$0BA@UTListSLock@@@@QEAAPEAVSOS_Node@@XZ; TList<NodeManager,SOS_Node,16,TListSLock>::GetTail(void)
0x10040caee  mov     qword ptr [rsp+58h+var_30+8], rax
0x10040caf3  xor     edx, edx; struct SOS_Node *
0x10040caf5  lea     rcx, [rsp+58h+var_30]; this
0x10040cafa  call    ?GetNext@SOS_NodeEnumIncludeUninitializedNodes@@QEAAPEAVSOS_Node@@PEAV2@@Z; SOS_NodeEnumIncludeUninitializedNodes::GetNext(SOS_Node *)
0x10040caff  mov     rbx, rax
0x10040cb02  test    rax, rax
0x10040cb05  jz      short loc_10040CB25
0x10040cb07  test    byte ptr [rbx+620h], 10h
0x10040cb0e  jz      short loc_10040CB25
0x10040cb10  mov     rdx, rbx; struct SOS_Node *
0x10040cb13  lea     rcx, [rsp+58h+var_30]; this
0x10040cb18  call    ?GetNext@SOS_NodeEnumIncludeUninitializedNodes@@QEAAPEAVSOS_Node@@PEAV2@@Z; SOS_NodeEnumIncludeUninitializedNodes::GetNext(SOS_Node *)
0x10040cb1d  mov     rbx, rax
0x10040cb20  test    rax, rax
0x10040cb23  jnz     short loc_10040CB07
0x10040cb25  test    rbx, rbx
0x10040cb28  jz      short loc_10040CBA3
0x10040cb2a  nop     word ptr [rax+rax]
0x10040cb2f  nop
0x10040cb30  mov     rax, cs:__imp_?sm_isIdleDetectionEnabled@SOS_PublicGlobals@@2HA; int SOS_PublicGlobals::sm_isIdleDetectionEnabled
0x10040cb37  cmp     dword ptr [rax], 0
0x10040cb3a  jz      short loc_10040CB69
0x10040cb3c  lea     rcx, [rbx+788h]; lpSystemTimeAsFileTime
0x10040cb43  call    cs:__imp_GetSystemTimeAsFileTime
0x10040cb49  mov     eax, [rbx+110h]
0x10040cb4f  test    eax, eax
0x10040cb51  jz      short loc_10040CB69
0x10040cb53  mov     [rbx+110h], edi
0x10040cb59  mov     ecx, edi
0x10040cb5b  cmp     eax, 2
0x10040cb5e  setz    cl
0x10040cb61  xor     edx, edx
0x10040cb63  call    cs:__imp_?WakeUpSuspendedNodes@ResourceMonitor@@SAXHW4WakeUpReason@@@Z; ResourceMonitor::WakeUpSuspendedNodes(int,WakeUpReason)
0x10040cb69  mov     rdx, rbx; struct SOS_Node *
0x10040cb6c  lea     rcx, [rsp+58h+var_30]; this
0x10040cb71  call    ?GetNext@SOS_NodeEnumIncludeUninitializedNodes@@QEAAPEAVSOS_Node@@PEAV2@@Z; SOS_NodeEnumIncludeUninitializedNodes::GetNext(SOS_Node *)
0x10040cb76  mov     rbx, rax
0x10040cb79  test    rax, rax
0x10040cb7c  jz      short loc_10040CB9E
0x10040cb7e  nop
0x10040cb7f  nop
0x10040cb80  test    byte ptr [rbx+620h], 10h
0x10040cb87  jz      short loc_10040CB9E
0x10040cb89  mov     rdx, rbx; struct SOS_Node *
0x10040cb8c  lea     rcx, [rsp+58h+var_30]; this
0x10040cb91  call    ?GetNext@SOS_NodeEnumIncludeUninitializedNodes@@QEAAPEAVSOS_Node@@PEAV2@@Z; SOS_NodeEnumIncludeUninitializedNodes::GetNext(SOS_Node *)
0x10040cb96  mov     rbx, rax
0x10040cb99  test    rax, rax
0x10040cb9c  jnz     short loc_10040CB80
0x10040cb9e  test    rbx, rbx
0x10040cba1  jnz     short loc_10040CB30
0x10040cba3  mov     edx, 3
0x10040cba8  xor     ecx, ecx
0x10040cbaa  call    cs:__imp_?WakeUpSuspendedNodes@ResourceMonitor@@SAXHW4WakeUpReason@@@Z; ResourceMonitor::WakeUpSuspendedNodes(int,WakeUpReason)
0x10040cbb0  mov     rax, cs:__imp_?sm_isIdleDetectionEnabled@SOS_PublicGlobals@@2HA; int SOS_PublicGlobals::sm_isIdleDetectionEnabled
0x10040cbb7  mov     [rax], edi
0x10040cbb9  lea     rcx, [rsp+58h+var_30]; this
0x10040cbbe  call    ??1SOS_NodeEnumIncludeUninitializedNodes@@QEAA@XZ; SOS_NodeEnumIncludeUninitializedNodes::~SOS_NodeEnumIncludeUninitializedNodes(void)
0x10040cbc3  mov     rbx, [rsp+58h+arg_0]
0x10040cbc8  add     rsp, 50h
0x10040cbcc  pop     rdi
0x10040cbcd  retn
```

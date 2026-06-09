# ServerBFEHandler::RemovePolicyForMap(ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP *)

- ea: `0x1800400a8`
- end: `0x180040301`
- name: `?RemovePolicyForMap@ServerBFEHandler@@KAKPEAU_VPNIKE_INTERFACE_POLICY_MAP@1@@Z`
- size: `601`
- prototype: `__int64 __fastcall(struct ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003b62c`
- `0x18003fed8`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18002e6f4`
- `0x18003fd14`
- `0x1800400a8`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040292`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040292`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040284`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040284`

## string_xrefs

- `0x180040172`: `ServerBFEHandler::RemovePolicyForMap`
- `0x180040239`: `RemovePolicy failed: %u`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServerBFEHandler::RemovePolicyForMap(struct ServerBFEHandler::_VPNIKE_INTERFACE_POLICY_MAP *a1)
{
  unsigned int BfeHandle; // eax
  unsigned int i; // edi
  GUID *v4; // rcx
  __int64 v5; // rax
  unsigned int v6; // eax
  unsigned int v7; // esi
  void *v8; // rdi
  HANDLE ProcessHeap; // rax
  unsigned int v10; // ebx
  unsigned int v12; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+28h] [rbp-D8h]
  __int64 v14; // [rsp+30h] [rbp-D0h]
  void *v15; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+48h] [rbp-B8h]
  __int128 v18; // [rsp+58h] [rbp-A8h]
  __int64 v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+70h] [rbp-90h]
  int v21; // [rsp+74h] [rbp-8Ch]
  int v22; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
  }
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v12 = 0;
  v15 = 0;
  v13 = 0;
  v14 = 0;
  v17 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v20 = -1;
  v21 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v16,
      L"ServerBFEHandler::RemovePolicyForMap",
      &v12,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  BfeHandle = BFEHandler::GetBfeHandle(&v15);
  v12 = BfeHandle;
  if ( v15 )
  {
    for ( i = 0; i < *((_DWORD *)a1 + 4); ++i )
    {
      v4 = (GUID *)(*((_QWORD *)a1 + 3) + 16LL * i);
      v5 = *(_QWORD *)&v4->Data1 - v13;
      if ( *(_QWORD *)&v4->Data1 == v13 )
        v5 = *(_QWORD *)v4->Data4 - v14;
      if ( v5 )
      {
        v6 = ServerBFEHandler::RemovePolicy(v4);
        v7 = 0;
        if ( v6 != -2144206840 )
          v7 = v6;
        if ( v7 )
        {
          if ( (byte_1800AA941 & 4) != 0 )
          {
            LOWORD(v22) = 0;
            FormatRRASErrorString(&v22, L"RemovePolicy failed: %u", v7);
            if ( (byte_1800AA941 & 4) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v22);
          }
          if ( !v12 )
            v12 = v7;
        }
      }
    }
    v8 = (void *)*((_QWORD *)a1 + 3);
    if ( v8 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v8);
      *((_QWORD *)a1 + 3) = 0;
    }
    *((_DWORD *)a1 + 4) = 0;
  }
  else if ( (byte_1800AA941 & 4) != 0 )
  {
    LOWORD(v22) = 0;
    FormatRRASErrorString(&v22, L"GetBfeHandle failed: %d", BfeHandle);
    if ( (byte_1800AA941 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v22);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids, v12);
  }
  v10 = v12;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v16);
  return v10;
}

```

## disassembly

```asm
0x1800400a8  push    rbp
0x1800400aa  push    rbx
0x1800400ab  push    rsi
0x1800400ac  push    rdi
0x1800400ad  push    r14
0x1800400af  push    r15
0x1800400b1  lea     rbp, [rsp-798h]
0x1800400b9  sub     rsp, 898h
0x1800400c0  mov     rax, cs:__security_cookie
0x1800400c7  xor     rax, rsp
0x1800400ca  mov     [rbp+7C0h+var_40], rax
0x1800400d1  mov     rbx, rcx
0x1800400d4  lea     r15, WPP_GLOBAL_Control
0x1800400db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800400e2  cmp     rcx, r15
0x1800400e5  jz      short loc_180040108
0x1800400e7  test    byte ptr [rcx+1Ch], 1
0x1800400eb  jz      short loc_180040108
0x1800400ed  cmp     byte ptr [rcx+19h], 6
0x1800400f1  jb      short loc_180040108
0x1800400f3  mov     edx, 2Bh ; '+'
0x1800400f8  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x1800400ff  mov     rcx, [rcx+10h]
0x180040103  call    WPP_SF_
0x180040108  xor     r14d, r14d
0x18004010b  mov     [rbp+7C0h+var_840], r14d
0x18004010f  xor     edx, edx; Val
0x180040111  mov     r8d, 7FCh; Size
0x180040117  lea     rcx, [rbp+7C0h+var_83C]; void *
0x18004011b  call    memset_0
0x180040120  mov     [rsp+8C0h+var_8A0], r14d
0x180040125  mov     [rsp+8C0h+var_888], r14
0x18004012a  mov     [rsp+8C0h+var_898], r14
0x18004012f  mov     [rsp+8C0h+var_890], r14
0x180040134  xorps   xmm0, xmm0
0x180040137  movdqu  [rsp+8C0h+var_878], xmm0
0x18004013d  mov     [rsp+8C0h+var_880], r14
0x180040142  xorps   xmm1, xmm1
0x180040145  movdqu  [rsp+8C0h+var_868], xmm1
0x18004014b  mov     [rsp+8C0h+var_858], r14
0x180040150  mov     [rsp+8C0h+var_850], 0FFFFFFFFh
0x180040158  mov     [rsp+8C0h+var_84C], r14d
0x18004015d  test    cs:byte_1800AA941, 8
0x180040164  jz      short loc_180040183
0x180040166  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18004016d  lea     r8, [rsp+8C0h+var_8A0]; unsigned int *
0x180040172  lea     rdx, aServerbfehandl_2; "ServerBFEHandler::RemovePolicyForMap"
0x180040179  lea     rcx, [rsp+8C0h+var_880]; this
0x18004017e  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180040183  lea     rcx, [rsp+8C0h+var_888]; void **
0x180040188  call    ?GetBfeHandle@BFEHandler@@SAKPEAPEAX@Z; BFEHandler::GetBfeHandle(void * *)
0x18004018d  mov     [rsp+8C0h+var_8A0], eax
0x180040191  cmp     [rsp+8C0h+var_888], r14
0x180040196  jnz     short loc_1800401E6
0x180040198  test    cs:byte_1800AA941, 4
0x18004019f  jz      loc_1800402A0
0x1800401a5  mov     word ptr [rbp+7C0h+var_840], r14w
0x1800401aa  mov     r8d, eax
0x1800401ad  lea     rdx, aGetbfehandleFa; "GetBfeHandle failed: %d"
0x1800401b4  lea     rcx, [rbp+7C0h+var_840]
0x1800401b8  call    FormatRRASErrorString
0x1800401bd  test    cs:byte_1800AA941, 4
0x1800401c4  jz      loc_1800402A0
0x1800401ca  lea     r8, [rbp+7C0h+var_840]
0x1800401ce  lea     rdx, RasVpnIkeTraceError
0x1800401d5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800401dc  call    McTemplateU0z_EventWriteTransfer
0x1800401e1  jmp     loc_1800402A0
0x1800401e6  mov     edi, r14d
0x1800401e9  cmp     edi, [rbx+10h]
0x1800401ec  jnb     loc_18004027B
0x1800401f2  mov     ecx, edi
0x1800401f4  shl     rcx, 4
0x1800401f8  add     rcx, [rbx+18h]; key
0x1800401fc  mov     rax, [rcx]
0x1800401ff  sub     rax, [rsp+8C0h+var_898]
0x180040204  jnz     short loc_18004020F
0x180040206  mov     rax, [rcx+8]
0x18004020a  sub     rax, [rsp+8C0h+var_890]
0x18004020f  test    rax, rax
0x180040212  jz      short loc_180040274
0x180040214  call    ?RemovePolicy@ServerBFEHandler@@KAKAEAU_GUID@@@Z; ServerBFEHandler::RemovePolicy(_GUID &)
0x180040219  mov     esi, r14d
0x18004021c  cmp     eax, 80320008h
0x180040221  cmovnz  esi, eax
0x180040224  test    esi, esi
0x180040226  jz      short loc_180040274
0x180040228  test    cs:byte_1800AA941, 4
0x18004022f  jz      short loc_180040269
0x180040231  mov     word ptr [rbp+7C0h+var_840], r14w
0x180040236  mov     r8d, esi
0x180040239  lea     rdx, aRemovepolicyFa; "RemovePolicy failed: %u"
0x180040240  lea     rcx, [rbp+7C0h+var_840]
0x180040244  call    FormatRRASErrorString
0x180040249  test    cs:byte_1800AA941, 4
0x180040250  jz      short loc_180040269
0x180040252  lea     r8, [rbp+7C0h+var_840]
0x180040256  lea     rdx, RasVpnIkeTraceError
0x18004025d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180040264  call    McTemplateU0z_EventWriteTransfer
0x180040269  cmp     [rsp+8C0h+var_8A0], r14d
0x18004026e  jnz     short loc_180040274
0x180040270  mov     [rsp+8C0h+var_8A0], esi
0x180040274  inc     edi
0x180040276  jmp     loc_1800401E9
0x18004027b  mov     rdi, [rbx+18h]
0x18004027f  test    rdi, rdi
0x180040282  jz      short loc_18004029C
0x180040284  call    cs:__imp_GetProcessHeap
0x18004028a  mov     r8, rdi; lpMem
0x18004028d  xor     edx, edx; dwFlags
0x18004028f  mov     rcx, rax; hHeap
0x180040292  call    cs:__imp_HeapFree
0x180040298  mov     [rbx+18h], r14
0x18004029c  mov     [rbx+10h], r14d
0x1800402a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800402a7  cmp     rcx, r15
0x1800402aa  jz      short loc_1800402D2
0x1800402ac  test    byte ptr [rcx+1Ch], 1
0x1800402b0  jz      short loc_1800402D2
0x1800402b2  cmp     byte ptr [rcx+19h], 6
0x1800402b6  jb      short loc_1800402D2
0x1800402b8  mov     edx, 2Ch ; ','
0x1800402bd  mov     r9d, [rsp+8C0h+var_8A0]
0x1800402c2  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x1800402c9  mov     rcx, [rcx+10h]
0x1800402cd  call    WPP_SF_d
0x1800402d2  mov     ebx, [rsp+8C0h+var_8A0]
0x1800402d6  lea     rcx, [rsp+8C0h+var_880]; this
0x1800402db  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800402e0  mov     eax, ebx
0x1800402e2  mov     rcx, [rbp+7C0h+var_40]
0x1800402e9  xor     rcx, rsp; StackCookie
0x1800402ec  call    __security_check_cookie
0x1800402f1  add     rsp, 898h
0x1800402f8  pop     r15
0x1800402fa  pop     r14
0x1800402fc  pop     rdi
0x1800402fd  pop     rsi
0x1800402fe  pop     rbx
0x1800402ff  pop     rbp
0x180040300  retn
```

# Ssl::EnableLogTrace(void)

- ea: `0x10044beb0`
- end: `0x10044c0a2`
- name: `?EnableLogTrace@Ssl@@UEAAKXZ`
- size: `498`
- prototype: `unsigned int __fastcall(Ssl *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1004269b0`
- `0x10044beb0`
- `0x100487cd6`

## import_xrefs

- `sqldk!?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A` at `0x10044bef5`
- `sqldk!?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A` at `0x10044bfd7`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10044bfa5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10044bfa5`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10044bf11`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10044bf27`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10044bff3`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10044c00c`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10044bf11`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10044bf27`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10044bff3`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10044c00c`
- `sqldk!SystemThread_TlsIndex` at `0x10044bf3e`
- `sqldk!SystemThread_TlsOffset` at `0x10044bf47`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044bf62`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10044bf62`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x10044bf21`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x10044c003`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x10044bf21`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x10044c003`

## string_xrefs

- `0x10044bf93`: `sql\common\dk\sni\src\SNI_SslProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Ssl::EnableLogTrace(Ssl *this, __int64 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v5; // rbx
  PerProcessGlobals *ClientProcessGlobals; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rdi
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rbx
  PerProcessGlobals *v13; // rax
  struct MemoryClerk **DefaultMemoryClerksForNode; // rbx
  __m128i si128; // xmm0
  int v17; // [rsp+70h] [rbp+8h] BYREF
  int v18; // [rsp+78h] [rbp+10h]
  struct IMemObj *v19; // [rsp+80h] [rbp+18h]
  char *v20; // [rsp+88h] [rbp+20h]

  if ( *((_QWORD *)this + 168) )
    return 0;
  v17 = 0;
  SNIGetInfo(*((_QWORD *)this + 4), 13, (__int64)&v17, a4);
  v5 = SOS_PublicGlobals::sm_NodeManager[*(unsigned __int16 *)(*((_QWORD *)this + 4) + 12944LL) + 5];
  if ( v5 && (*(_BYTE *)(v5 + 1568) & 0x10) != 0 )
    v5 = 0;
  ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
  PerProcessGlobals::GetDefaultMemoryClerksForNode(ClientProcessGlobals, *(_WORD *)(v5 + 160));
  SOS_OS::GetClientProcessGlobals();
  v18 = 741;
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v8 = *(_QWORD *)(v7 + 256);
  if ( !v8 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v8 = *(_QWORD *)(v7 + 256);
  }
  v19 = *(struct IMemObj **)(*(_QWORD *)(*(_QWORD *)(v8 + 992) + 56LL) + 8LL);
  v9 = (char *)operator new(0x360u, v19, 1, "sql\\common\\dk\\sni\\src\\SNI_SslProvider.cpp", 741, 6u);
  v20 = v9;
  if ( v9 )
  {
    v10 = v17;
    v11 = *((_QWORD *)this + 4);
    *(_QWORD *)v9 = v11;
    *((_DWORD *)v9 + 4) = v10;
    *((_DWORD *)v9 + 5) = 0;
    v12 = SOS_PublicGlobals::sm_NodeManager[*(unsigned __int16 *)(v11 + 12944) + 5];
    if ( v12 )
    {
      if ( (*(_BYTE *)(v12 + 1568) & 0x10) != 0 )
        v12 = 0;
    }
    v13 = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
    DefaultMemoryClerksForNode = PerProcessGlobals::GetDefaultMemoryClerksForNode(v13, *(_WORD *)(v12 + 160));
    SOS_OS::GetClientProcessGlobals();
    *((_QWORD *)v9 + 1) = (**((__int64 (__fastcall ***)(__int64, _QWORD, _QWORD))DefaultMemoryClerksForNode[24] + 8))(
                            (__int64)DefaultMemoryClerksForNode[24] + 64,
                            (unsigned int)((*((_DWORD *)v9 + 4) >> 13) + 1),
                            0);
    memset_0(v9 + 24, 204, 0x190u);
    memset_0(v9 + 424, 204, 0x190u);
    si128 = _mm_load_si128((const __m128i *)&_xmm_cccccccccccccccccccccccccccccccc);
    *(__m128i *)(v9 + 824) = si128;
    *(__m128i *)(v9 + 840) = si128;
    *((_QWORD *)v9 + 107) = si128.m128i_i64[0];
  }
  else
  {
    v9 = 0;
  }
  *((_QWORD *)this + 168) = v9;
  if ( v9 )
    return 0;
  else
    return 14;
}

```

## disassembly

```asm
0x10044beb0  push    rbx
0x10044beb2  push    rbp
0x10044beb3  push    rsi
0x10044beb4  push    rdi
0x10044beb5  sub     rsp, 48h
0x10044beb9  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x10044bec2  mov     rsi, rcx
0x10044bec5  cmp     qword ptr [rcx+540h], 0
0x10044becd  jnz     loc_10044C097
0x10044bed3  xor     ebp, ebp
0x10044bed5  mov     [rsp+68h+arg_0], ebp
0x10044bed9  lea     r8, [rsp+68h+arg_0]
0x10044bede  lea     edx, [rbp+0Dh]
0x10044bee1  mov     rcx, [rcx+20h]
0x10044bee5  call    SNIGetInfo
0x10044beea  mov     rax, [rsi+20h]
0x10044beee  movzx   edx, word ptr [rax+3290h]
0x10044bef5  mov     rax, cs:__imp_?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A; NodeManager SOS_PublicGlobals::sm_NodeManager
0x10044befc  mov     rbx, [rax+rdx*8+28h]
0x10044bf01  test    rbx, rbx
0x10044bf04  jz      short loc_10044BF11
0x10044bf06  test    byte ptr [rbx+620h], 10h
0x10044bf0d  cmovnz  rbx, rbp
0x10044bf11  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x10044bf17  mov     rcx, rax
0x10044bf1a  movzx   edx, word ptr [rbx+0A0h]
0x10044bf21  call    cs:__imp_?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z; PerProcessGlobals::GetDefaultMemoryClerksForNode(ushort)
0x10044bf27  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x10044bf2d  mov     [rsp+68h+arg_8], 2E5h
0x10044bf35  mov     rdx, gs:58h
0x10044bf3e  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044bf45  mov     ecx, [rax]
0x10044bf47  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044bf4e  mov     ebx, [rax]
0x10044bf50  add     rbx, [rdx+rcx*8]
0x10044bf54  mov     rax, [rbx+100h]
0x10044bf5b  test    rax, rax
0x10044bf5e  jnz     short loc_10044BF6F
0x10044bf60  xor     ecx, ecx
0x10044bf62  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10044bf68  mov     rax, [rbx+100h]
0x10044bf6f  mov     rax, [rax+3E0h]
0x10044bf76  mov     rcx, [rax+38h]
0x10044bf7a  mov     rdx, [rcx+8]
0x10044bf7e  mov     [rsp+68h+arg_10], rdx
0x10044bf86  mov     [rsp+68h+var_40], 6
0x10044bf8b  mov     [rsp+68h+var_48], 2E5h
0x10044bf93  lea     r9, aSqlCommonDkSni_11; "sql\\common\\dk\\sni\\src\\SNI_SslProvi"...
0x10044bf9a  mov     ecx, 360h
0x10044bf9f  mov     r8d, 1
0x10044bfa5  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10044bfab  mov     rdi, rax
0x10044bfae  mov     [rsp+68h+arg_18], rax
0x10044bfb6  test    rax, rax
0x10044bfb9  jz      loc_10044C07C
0x10044bfbf  mov     eax, [rsp+68h+arg_0]
0x10044bfc3  mov     rcx, [rsi+20h]
0x10044bfc7  mov     [rdi], rcx
0x10044bfca  mov     [rdi+10h], eax
0x10044bfcd  mov     [rdi+14h], ebp
0x10044bfd0  movzx   ecx, word ptr [rcx+3290h]
0x10044bfd7  mov     rax, cs:__imp_?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A; NodeManager SOS_PublicGlobals::sm_NodeManager
0x10044bfde  mov     rbx, [rax+rcx*8+28h]
0x10044bfe3  test    rbx, rbx
0x10044bfe6  jz      short loc_10044BFF3
0x10044bfe8  test    byte ptr [rbx+620h], 10h
0x10044bfef  cmovnz  rbx, rbp
0x10044bff3  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x10044bff9  mov     rcx, rax
0x10044bffc  movzx   edx, word ptr [rbx+0A0h]
0x10044c003  call    cs:__imp_?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z; PerProcessGlobals::GetDefaultMemoryClerksForNode(ushort)
0x10044c009  mov     rbx, rax
0x10044c00c  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x10044c012  mov     rcx, [rbx+0C0h]
0x10044c019  mov     edx, [rdi+10h]
0x10044c01c  shr     edx, 0Dh
0x10044c01f  inc     edx
0x10044c021  add     rcx, 40h ; '@'
0x10044c025  mov     rax, [rcx]
0x10044c028  xor     r8d, r8d
0x10044c02b  call    qword ptr [rax]
0x10044c02d  mov     [rdi+8], rax
0x10044c031  lea     rcx, [rdi+18h]; void *
0x10044c035  mov     edx, 0CCh; Val
0x10044c03a  mov     r8d, 190h; Size
0x10044c040  call    memset_0
0x10044c045  lea     rcx, [rdi+1A8h]; void *
0x10044c04c  mov     edx, 0CCh; Val
0x10044c051  mov     r8d, 190h; Size
0x10044c057  call    memset_0
0x10044c05c  movdqa  xmm0, cs:__xmm@cccccccccccccccccccccccccccccccc
0x10044c064  movups  xmmword ptr [rdi+338h], xmm0
0x10044c06b  movups  xmmword ptr [rdi+348h], xmm0
0x10044c072  movq    qword ptr [rdi+358h], xmm0
0x10044c07a  jmp     short loc_10044C07F
0x10044c07c  mov     rdi, rbp
0x10044c07f  mov     [rsi+540h], rdi
0x10044c086  test    rdi, rdi
0x10044c089  jnz     short loc_10044C097
0x10044c08b  lea     eax, [rdi+0Eh]
0x10044c08e  add     rsp, 48h
0x10044c092  pop     rdi
0x10044c093  pop     rsi
0x10044c094  pop     rbp
0x10044c095  pop     rbx
0x10044c096  retn
0x10044c097  xor     eax, eax
0x10044c099  add     rsp, 48h
0x10044c09d  pop     rdi
0x10044c09e  pop     rsi
0x10044c09f  pop     rbp
0x10044c0a0  pop     rbx
0x10044c0a1  retn
```

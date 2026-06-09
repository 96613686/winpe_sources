# TpmStartSrkEkThread

- ea: `0x14001e394`
- end: `0x14001e598`
- name: `TpmStartSrkEkThread`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001db10`

## callees

- `0x1400078b8`
- `0x140009278`
- `0x140009fc8`
- `0x14001d14c`
- `0x14001d170`
- `0x14001e394`
- `0x140045158`
- `0x140045430`
- `0x1400454a0`

## pseudocode

```c
__int64 __fastcall TpmStartSrkEkThread(__int64 a1, __int64 a2, int a3, int a4)
{
  unsigned int v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  ThreadWithCancel *v7; // rax
  unsigned int v8; // edx
  ThreadWithCancel *v9; // rbx
  unsigned __int8 *v10; // rax
  unsigned __int8 *v11; // rdi
  int v13; // eax
  unsigned __int64 retaddr; // [rsp+48h] [rbp+0h]
  int v15; // [rsp+60h] [rbp+18h] BYREF
  int v16; // [rsp+68h] [rbp+20h] BYREF

  v16 = a4;
  v15 = a3;
  if ( TpmTransportType::m_Version != 2 )
    return (unsigned int)-1073741637;
  v15 = 0;
  v16 = 0;
  TpmRegistry::QueryValue(2, L"NoAutoProvision", 4, (__int64)&v15, 4u, 0);
  TpmRegistry::QueryValue(2, L"NoEarlyProvision", 4, (__int64)&v16, 4u, 0);
  if ( !v15 && !v16 || (v5 = 0, v16 == -1) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_6356bb85d3253aa80b2f75179e64f445_Traceguids);
    v7 = (ThreadWithCancel *)ThreadWithCancel::operator new((unsigned __int64)v6);
    v9 = v7;
    if ( !v7 )
      return (unsigned int)-1073741670;
    *((_QWORD *)v7 + 1) = 0;
    *(_QWORD *)v7 = Tpm20WindowsKeyCreation_Thread;
    *((_QWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 3) = 0;
    if ( _InterlockedCompareExchange64(
           (volatile signed __int64 *)&g_Tpm20WindowsKeyCreationThread,
           (signed __int64)v7,
           0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_6356bb85d3253aa80b2f75179e64f445_Traceguids);
      ThreadWithCancel::`scalar deleting destructor'(v9, v8);
      return (unsigned int)-1073278049;
    }
    v10 = TpmAlloc(1, 0x20u, retaddr);
    v11 = v10;
    if ( !v10 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_6356bb85d3253aa80b2f75179e64f445_Traceguids);
      return (unsigned int)-1073741670;
    }
    *(_DWORD *)v10 = 3;
    *((_QWORD *)v10 + 1) = a1;
    *((_QWORD *)v10 + 2) = 0;
    *((_DWORD *)v10 + 6) = 10;
    v13 = ThreadWithCancel::Start(g_Tpm20WindowsKeyCreationThread, v10);
    v5 = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_6356bb85d3253aa80b2f75179e64f445_Traceguids,
          (unsigned int)v13);
      TpmFree(v11);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14001e394  mov     [rsp+arg_0], rbx
0x14001e399  mov     [rsp+arg_18], r9d
0x14001e39e  mov     [rsp+arg_10], r8d
0x14001e3a3  push    rsi
0x14001e3a4  push    rdi
0x14001e3a5  push    r15
0x14001e3a7  sub     rsp, 30h
0x14001e3ab  cmp     cs:?m_Version@TpmTransportType@@0W4VERSION@1@A, 2; TpmTransportType::VERSION TpmTransportType::m_Version
0x14001e3b2  mov     rsi, rcx
0x14001e3b5  jz      short loc_14001E3C1
0x14001e3b7  mov     ebx, 0C00000BBh
0x14001e3bc  jmp     loc_14001E523
0x14001e3c1  mov     edi, 4
0x14001e3c6  mov     [rsp+48h+var_20], 0
0x14001e3cf  lea     r9, [rsp+48h+arg_10]
0x14001e3d4  mov     [rsp+48h+arg_10], 0
0x14001e3dc  mov     r8d, edi
0x14001e3df  mov     [rsp+48h+arg_18], 0
0x14001e3e7  lea     rdx, aNoautoprovisio; "NoAutoProvision"
0x14001e3ee  mov     [rsp+48h+var_28], edi
0x14001e3f2  lea     ecx, [rdi-2]
0x14001e3f5  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x14001e3fa  lea     r9, [rsp+48h+arg_18]
0x14001e3ff  mov     [rsp+48h+var_20], 0
0x14001e408  mov     r8d, edi
0x14001e40b  mov     [rsp+48h+var_28], edi
0x14001e40f  lea     rdx, aNoearlyprovisi; "NoEarlyProvision"
0x14001e416  lea     ecx, [rdi-2]
0x14001e419  call    ?QueryValue@TpmRegistry@@SAJW4KEY_VALUES@1@PEBGKPEAXKPEAK@Z; TpmRegistry::QueryValue(TpmRegistry::KEY_VALUES,ushort const *,ulong,void *,ulong,ulong *)
0x14001e41e  cmp     [rsp+48h+arg_10], 0
0x14001e423  mov     eax, [rsp+48h+arg_18]
0x14001e427  jnz     short loc_14001E42D
0x14001e429  test    eax, eax
0x14001e42b  jz      short loc_14001E438
0x14001e42d  xor     ebx, ebx
0x14001e42f  cmp     eax, 0FFFFFFFFh
0x14001e432  jnz     loc_14001E523
0x14001e438  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001e43f  lea     r15, WPP_GLOBAL_Control
0x14001e446  cmp     rcx, r15
0x14001e449  jz      short loc_14001E468
0x14001e44b  mov     eax, [rcx+2Ch]
0x14001e44e  test    dil, al
0x14001e451  jz      short loc_14001E468
0x14001e453  mov     rcx, [rcx+18h]
0x14001e457  lea     r8, WPP_6356bb85d3253aa80b2f75179e64f445_Traceguids
0x14001e45e  mov     edx, 0Ah
0x14001e463  call    WPP_SF_
0x14001e468  call    ??2ThreadWithCancel@@SAPEAX_K@Z; ThreadWithCancel::operator new(unsigned __int64)
0x14001e46d  mov     rbx, rax
0x14001e470  test    rax, rax
0x14001e473  jz      loc_14001E51E
0x14001e479  lea     rax, ?Tpm20WindowsKeyCreation_Thread@@YAXPEAX@Z; Tpm20WindowsKeyCreation_Thread(void *)
0x14001e480  mov     qword ptr [rbx+8], 0
0x14001e488  mov     [rbx], rax
0x14001e48b  xor     eax, eax
0x14001e48d  mov     qword ptr [rbx+10h], 0
0x14001e495  mov     qword ptr [rbx+18h], 0
0x14001e49d  lock cmpxchg cs:g_Tpm20WindowsKeyCreationThread, rbx
0x14001e4a6  jz      short loc_14001E4DF
0x14001e4a8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001e4af  cmp     rcx, r15
0x14001e4b2  jz      short loc_14001E4D0
0x14001e4b4  mov     eax, [rcx+2Ch]
0x14001e4b7  test    al, 2
0x14001e4b9  jz      short loc_14001E4D0
0x14001e4bb  mov     rcx, [rcx+18h]
0x14001e4bf  lea     r8, WPP_6356bb85d3253aa80b2f75179e64f445_Traceguids
0x14001e4c6  mov     edx, 0Bh
0x14001e4cb  call    WPP_SF_
0x14001e4d0  mov     rcx, rbx; this
0x14001e4d3  call    ??_GThreadWithCancel@@QEAAPEAXI@Z; ThreadWithCancel::`scalar deleting destructor'(uint)
0x14001e4d8  mov     ebx, 0C007139Fh
0x14001e4dd  jmp     short loc_14001E523
0x14001e4df  mov     r8, [rsp+48h]; unsigned __int64
0x14001e4e4  mov     edx, 20h ; ' '; unsigned __int64
0x14001e4e9  mov     cl, 1; bool
0x14001e4eb  call    ?TpmAlloc@@YAPEAE_N_K1@Z; TpmAlloc(bool,unsigned __int64,unsigned __int64)
0x14001e4f0  mov     rdi, rax
0x14001e4f3  test    rax, rax
0x14001e4f6  jnz     short loc_14001E534
0x14001e4f8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001e4ff  cmp     rcx, r15
0x14001e502  jz      short loc_14001E51E
0x14001e504  mov     eax, [rcx+2Ch]
0x14001e507  test    al, 2
0x14001e509  jz      short loc_14001E51E
0x14001e50b  mov     rcx, [rcx+18h]
0x14001e50f  lea     edx, [rdi+0Ch]
0x14001e512  lea     r8, WPP_6356bb85d3253aa80b2f75179e64f445_Traceguids
0x14001e519  call    WPP_SF_
0x14001e51e  mov     ebx, 0C000009Ah
0x14001e523  mov     eax, ebx
0x14001e525  mov     rbx, [rsp+48h+arg_0]
0x14001e52a  add     rsp, 30h
0x14001e52e  pop     r15
0x14001e530  pop     rdi
0x14001e531  pop     rsi
0x14001e532  retn
0x14001e534  mov     dword ptr [rax], 3
0x14001e53a  mov     rdx, rdi; void *
0x14001e53d  mov     [rax+8], rsi
0x14001e541  mov     qword ptr [rax+10h], 0
0x14001e549  mov     dword ptr [rax+18h], 0Ah
0x14001e550  mov     rcx, cs:g_Tpm20WindowsKeyCreationThread; this
0x14001e557  call    ?Start@ThreadWithCancel@@QEAAJPEAX@Z; ThreadWithCancel::Start(void *)
0x14001e55c  mov     ebx, eax
0x14001e55e  test    eax, eax
0x14001e560  jns     short loc_14001E523
0x14001e562  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001e569  cmp     rcx, r15
0x14001e56c  jz      short loc_14001E58E
0x14001e56e  mov     edx, [rcx+2Ch]
0x14001e571  test    dl, 2
0x14001e574  jz      short loc_14001E58E
0x14001e576  mov     rcx, [rcx+18h]
0x14001e57a  lea     r8, WPP_6356bb85d3253aa80b2f75179e64f445_Traceguids
0x14001e581  mov     edx, 0Dh
0x14001e586  mov     r9d, eax
0x14001e589  call    WPP_SF_d
0x14001e58e  mov     rcx, rdi; void *
0x14001e591  call    ?TpmFree@@YAXPEAX@Z; TpmFree(void *)
0x14001e596  jmp     short loc_14001E523
```

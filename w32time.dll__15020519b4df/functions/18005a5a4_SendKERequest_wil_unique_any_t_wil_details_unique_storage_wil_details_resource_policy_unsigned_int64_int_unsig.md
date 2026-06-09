# SendKERequest(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> const &,_SecHandle &,_SecPkgContext_StreamSizes const &,std::vector<ushort,std::allocator<ushort>> const &)

- ea: `0x18005a5a4`
- end: `0x18005a782`
- name: `?SendKERequest@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEAU_SecHandle@@AEBU_SecPkgContext_StreamSizes@@AEBV?$vector@GV?$allocator@G@std@@@std@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005997c`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`
- `0x18003d2d8`
- `0x18003f3ec`
- `0x18003f491`
- `0x180045abc`
- `0x180059620`
- `0x180059890`
- `0x18005a5a4`

## import_xrefs

- `WS2_32!__imp_send` at `0x18005a6ff`
- `WS2_32!__imp_send` at `0x18005a6ff`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a714`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a714`
- `SspiCli!EncryptMessage` at `0x18005a6c1`
- `SspiCli!EncryptMessage` at `0x18005a6c1`

## string_xrefs

- `0x18005a600`: `onecore\ds\security\services\w32time\nts\ntske.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SendKERequest(SOCKET *a1, struct _SecHandle *a2, unsigned int *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  char *v8; // rbx
  char *v9; // r14
  int Error; // eax
  char *buf; // [rsp+28h] [rbp-81h] BYREF
  void **v13; // [rsp+30h] [rbp-79h] BYREF
  char v14; // [rsp+38h] [rbp-71h]
  char **p_buf; // [rsp+48h] [rbp-61h] BYREF
  struct _SecBufferDesc pMessage; // [rsp+50h] [rbp-59h] BYREF
  _DWORD v17[2]; // [rsp+60h] [rbp-49h] BYREF
  char *v18; // [rsp+68h] [rbp-41h]
  int v19; // [rsp+70h] [rbp-39h]
  int v20; // [rsp+74h] [rbp-35h]
  char *v21; // [rsp+78h] [rbp-31h]
  unsigned int v22; // [rsp+80h] [rbp-29h]
  int v23; // [rsp+84h] [rbp-25h]
  char *v24; // [rsp+88h] [rbp-21h]
  __int64 v25; // [rsp+90h] [rbp-19h]
  __int64 v26; // [rsp+98h] [rbp-11h]
  _BYTE Src[24]; // [rsp+A0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  memset(Src, 0, 22);
  v6 = BuildKERequest(Src);
  v7 = v6;
  if ( v6 >= 0 )
  {
    buf = (char *)operator new[](a3[1] + *a3 + a3[2]);
    p_buf = &buf;
    wil::scope_exit__lambda_5b0cea69da2f2023c814ebef0d37cd7f___(&v13, &p_buf);
    v8 = buf;
    v9 = &buf[*a3];
    memcpy_0(v9, Src, 0);
    v26 = 0;
    v18 = v8;
    v17[0] = *a3;
    v17[1] = 7;
    v21 = v9;
    v19 = 0;
    v20 = 1;
    v24 = v9;
    v22 = a3[1];
    v23 = 6;
    v25 = 0;
    pMessage.ulVersion = 0;
    pMessage.cBuffers = 4;
    pMessage.pBuffers = (PSecBuffer)v17;
    v7 = EncryptMessage(a2, 0, &pMessage, 0);
    if ( (v7 & 0x80000000) == 0 )
    {
      if ( ((send(*a1, buf, v17[0] + v22 + v19, 0) + 1) & 0xFFFFFFFE) == 0 )
      {
        Error = WSAGetLastError();
        v7 = Error;
        if ( Error > 0 )
          v7 = (unsigned __int16)Error | 0x80070000;
        if ( (unsigned __int8)FileLogAllowEntry(0) )
          FileLogAdd(L"SendKERequest: Sending on socket failed with hr: 0x%08X\n", v7);
      }
    }
    else if ( (unsigned __int8)FileLogAllowEntry(0) )
    {
      FileLogAdd(L"SendKERequest: EncryptMessage failed with hr: 0x%08X\n", v7);
    }
    if ( v14 )
    {
      v14 = 0;
      operator delete(*v13);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\ds\\security\\services\\w32time\\nts\\ntske.cpp",
      (const char *)(unsigned int)v6,
      0);
  }
  return v7;
}

```

## disassembly

```asm
0x18005a5a4  push    rbp
0x18005a5a6  push    rbx
0x18005a5a7  push    rsi
0x18005a5a8  push    rdi
0x18005a5a9  push    r12
0x18005a5ab  push    r13
0x18005a5ad  push    r14
0x18005a5af  push    r15
0x18005a5b1  lea     rbp, [rsp-1Fh]
0x18005a5b6  sub     rsp, 0C8h
0x18005a5bd  mov     rax, cs:__security_cookie
0x18005a5c4  xor     rax, rsp
0x18005a5c7  mov     [rbp+57h+var_48], rax
0x18005a5cb  mov     r15, r8
0x18005a5ce  mov     r13, rdx
0x18005a5d1  mov     r12, rcx
0x18005a5d4  xorps   xmm0, xmm0
0x18005a5d7  xor     eax, eax
0x18005a5d9  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18005a5dd  mov     qword ptr [rbp+57h+Src+0Eh], rax
0x18005a5e1  mov     dword ptr [rsp+100h+Size], eax; int
0x18005a5e5  lea     r8, [rsp+100h+Size]
0x18005a5ea  lea     rcx, [rbp+57h+Src]; void *
0x18005a5ee  call    ?BuildKERequest@@YAJPEAXKPEAKAEBV?$vector@GV?$allocator@G@std@@@std@@@Z; BuildKERequest(void *,ulong,ulong *,std::vector<ushort> const &)
0x18005a5f3  mov     ebx, eax
0x18005a5f5  test    eax, eax
0x18005a5f7  jns     short loc_18005A616
0x18005a5f9  mov     rcx, [rbp+5Fh]; this
0x18005a5fd  mov     r9d, eax; char *
0x18005a600  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\services\\w32tim"...
0x18005a607  mov     edx, 9Dh; void *
0x18005a60c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a611  jmp     loc_18005A75F
0x18005a616  mov     ecx, [r15+8]
0x18005a61a  add     ecx, [r15]
0x18005a61d  add     ecx, [r15+4]; unsigned __int64
0x18005a621  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005a626  mov     [rsp+100h+buf], rax
0x18005a62b  lea     rax, [rsp+100h+buf]
0x18005a630  mov     [rbp+57h+var_B8], rax
0x18005a634  lea     rdx, [rbp+57h+var_B8]
0x18005a638  lea     rcx, [rbp+57h+var_D0]
0x18005a63c  call    wil__scope_exit__lambda_5b0cea69da2f2023c814ebef0d37cd7f___
0x18005a641  nop
0x18005a642  mov     rbx, [rsp+100h+buf]
0x18005a647  mov     r14d, [r15]
0x18005a64a  add     r14, rbx
0x18005a64d  mov     edi, dword ptr [rsp+100h+Size]
0x18005a651  mov     r8d, edi; Size
0x18005a654  lea     rdx, [rbp+57h+Src]; Src
0x18005a658  mov     rcx, r14; void *
0x18005a65b  call    memcpy_0
0x18005a660  mov     [rbp+57h+var_68], 0
0x18005a668  mov     [rbp+57h+var_98], rbx
0x18005a66c  mov     eax, [r15]
0x18005a66f  mov     [rbp+57h+var_A0], eax
0x18005a672  mov     [rbp+57h+var_9C], 7
0x18005a679  mov     [rbp+57h+var_88], r14
0x18005a67d  mov     [rbp+57h+var_90], edi
0x18005a680  mov     [rbp+57h+var_8C], 1
0x18005a687  lea     rax, [rdi+r14]
0x18005a68b  mov     [rbp+57h+var_78], rax
0x18005a68f  mov     eax, [r15+4]
0x18005a693  mov     [rbp+57h+var_80], eax
0x18005a696  mov     [rbp+57h+var_7C], 6
0x18005a69d  xor     edi, edi
0x18005a69f  mov     [rbp+57h+var_70], rdi
0x18005a6a3  mov     [rbp+57h+pMessage.ulVersion], edi
0x18005a6a6  mov     [rbp+57h+pMessage.cBuffers], 4
0x18005a6ad  lea     rax, [rbp+57h+var_A0]
0x18005a6b1  mov     [rbp+57h+pMessage.pBuffers], rax
0x18005a6b5  xor     r9d, r9d; MessageSeqNo
0x18005a6b8  lea     r8, [rbp+57h+pMessage]; pMessage
0x18005a6bc  xor     edx, edx; fQOP
0x18005a6be  mov     rcx, r13; phContext
0x18005a6c1  call    cs:__imp_EncryptMessage
0x18005a6c8  nop     dword ptr [rax+rax+00h]
0x18005a6cd  mov     ebx, eax
0x18005a6cf  test    eax, eax
0x18005a6d1  jns     short loc_18005A6E7
0x18005a6d3  xor     ecx, ecx
0x18005a6d5  call    FileLogAllowEntry
0x18005a6da  test    al, al
0x18005a6dc  jz      short loc_18005A749
0x18005a6de  lea     rcx, aSendkerequestE; "SendKERequest: EncryptMessage failed wi"...
0x18005a6e5  jmp     short loc_18005A741
0x18005a6e7  mov     r8d, [rbp+57h+var_90]
0x18005a6eb  add     r8d, [rbp+57h+var_80]
0x18005a6ef  add     r8d, [rbp+57h+var_A0]; len
0x18005a6f3  xor     r9d, r9d; flags
0x18005a6f6  mov     rdx, [rsp+100h+buf]; buf
0x18005a6fb  mov     rcx, [r12]; s
0x18005a6ff  call    cs:__imp_send
0x18005a706  nop     dword ptr [rax+rax+00h]
0x18005a70b  inc     eax
0x18005a70d  test    eax, 0FFFFFFFEh
0x18005a712  jnz     short loc_18005A749
0x18005a714  call    cs:__imp_WSAGetLastError
0x18005a71b  nop     dword ptr [rax+rax+00h]
0x18005a720  mov     ebx, eax
0x18005a722  test    eax, eax
0x18005a724  jle     short loc_18005A72F
0x18005a726  movzx   ebx, ax
0x18005a729  or      ebx, 80070000h
0x18005a72f  xor     ecx, ecx
0x18005a731  call    FileLogAllowEntry
0x18005a736  test    al, al
0x18005a738  jz      short loc_18005A749
0x18005a73a  lea     rcx, aSendkerequestS; "SendKERequest: Sending on socket failed"...
0x18005a741  mov     edx, ebx
0x18005a743  call    FileLogAdd
0x18005a748  nop
0x18005a749  cmp     [rbp+57h+var_C8], dil
0x18005a74d  jz      short loc_18005A75F
0x18005a74f  mov     rcx, [rbp+57h+var_D0]
0x18005a753  mov     [rbp+57h+var_C8], dil
0x18005a757  mov     rcx, [rcx]; void *
0x18005a75a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005a75f  mov     eax, ebx
0x18005a761  mov     rcx, [rbp+57h+var_48]
0x18005a765  xor     rcx, rsp; StackCookie
0x18005a768  call    __security_check_cookie
0x18005a76d  add     rsp, 0C8h
0x18005a774  pop     r15
0x18005a776  pop     r14
0x18005a778  pop     r13
0x18005a77a  pop     r12
0x18005a77c  pop     rdi
0x18005a77d  pop     rsi
0x18005a77e  pop     rbx
0x18005a77f  pop     rbp
0x18005a780  retn
```

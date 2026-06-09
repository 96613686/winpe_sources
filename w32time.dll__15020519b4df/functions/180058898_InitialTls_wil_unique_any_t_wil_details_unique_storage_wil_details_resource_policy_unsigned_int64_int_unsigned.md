# InitialTls(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_SecHandle &,_SecHandle &)

- ea: `0x180058898`
- end: `0x180058a53`
- name: `?InitialTls@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_SecHandle@@2@Z`
- size: `443`
- prototype: `__int64 __fastcall(SOCKET *, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180058a5c`

## callees

- `0x180018138`
- `0x18001d9a0`
- `0x18003d270`
- `0x18005876c`
- `0x180058844`
- `0x180058898`

## import_xrefs

- `WS2_32!__imp_send` at `0x1800589da`
- `WS2_32!__imp_send` at `0x1800589da`
- `WS2_32!__imp_WSAGetLastError` at `0x1800589ed`
- `WS2_32!__imp_WSAGetLastError` at `0x1800589ed`
- `SspiCli!InitializeSecurityContextW` at `0x180058999`
- `SspiCli!InitializeSecurityContextW` at `0x180058999`

## string_xrefs

- `0x1800589b9`: `InitialTls: InitializeSecurityContextW is not SEC_I_CONTINUE_NEEDED, it is: 0x%08X\n`

## pseudocode

```c
__int64 __fastcall InitialTls(SOCKET *a1, __int64 a2, __int64 a3)
{
  SEC_WCHAR *v4; // r8
  struct _SecHandle *phNewContext; // r9
  struct _SecHandle *v6; // r10
  unsigned int v7; // r11d
  unsigned int v8; // ebx
  int Error; // eax
  unsigned int pfContextAttr; // [rsp+60h] [rbp-A0h] BYREF
  struct _SecBuffer *v12; // [rsp+68h] [rbp-98h] BYREF
  char v13; // [rsp+70h] [rbp-90h]
  char **v14; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v15[2]; // [rsp+88h] [rbp-78h] BYREF
  _DWORD *v16; // [rsp+90h] [rbp-70h]
  struct _SecBufferDesc pOutput; // [rsp+98h] [rbp-68h] BYREF
  struct _SecBufferDesc pInput; // [rsp+A8h] [rbp-58h] BYREF
  char *buf[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v20; // [rsp+C8h] [rbp-38h]
  _DWORD v21[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int16 v22; // [rsp+E0h] [rbp-20h]
  __int64 v23; // [rsp+E2h] [rbp-1Eh]
  __int16 v24; // [rsp+EAh] [rbp-16h]

  v24 = 0;
  v21[0] = 16;
  v21[1] = 2;
  v22 = 8;
  v23 = 0x312F656B73746E07LL;
  v15[1] = 18;
  v16 = v21;
  v15[0] = 20;
  pInput.cBuffers = 1;
  pInput.pBuffers = (PSecBuffer)v15;
  pInput.ulVersion = 0;
  *(_OWORD *)buf = 0;
  v20 = 0;
  HIDWORD(buf[0]) = 2;
  DWORD1(v20) = 17;
  v14 = buf;
  wil::scope_exit__lambda_e809bc703c2f031fb314c3909cbf4963___(&v12, &v14, a2, a3);
  pOutput.cBuffers = v7;
  pOutput.pBuffers = (PSecBuffer)buf;
  pOutput.ulVersion = 0;
  pfContextAttr = 0;
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(SEC_WCHAR **)v4;
  v8 = InitializeSecurityContextW(v6, 0, v4, 0xC11Cu, 0, 0, &pInput, 0, phNewContext, &pOutput, &pfContextAttr, 0);
  if ( v8 == 590610 )
  {
    if ( !LODWORD(buf[0]) || !buf[1] || (unsigned int)(send(*a1, buf[1], (int)buf[0], 0) + 1) <= 1 )
    {
      Error = WSAGetLastError();
      v8 = Error;
      if ( Error > 0 )
        v8 = (unsigned __int16)Error | 0x80070000;
      if ( (unsigned __int8)FileLogAllowEntry(0) )
        FileLogAdd(L"InitialTls: Sending on socket failed with: 0x%08X\n", v8);
    }
  }
  else if ( (unsigned __int8)FileLogAllowEntry(0) )
  {
    FileLogAdd(L"InitialTls: InitializeSecurityContextW is not SEC_I_CONTINUE_NEEDED, it is: 0x%08X\n", v8);
  }
  if ( v13 )
  {
    v13 = 0;
    FreeOutBuffers(v12);
  }
  return v8;
}

```

## disassembly

```asm
0x180058898  push    rbp
0x18005889a  push    rbx
0x18005889b  push    rsi
0x18005889c  push    rdi
0x18005889d  lea     rbp, [rsp-8]
0x1800588a2  sub     rsp, 108h
0x1800588a9  mov     rax, cs:__security_cookie
0x1800588b0  xor     rax, rsp
0x1800588b3  mov     [rbp+20h+var_30], rax
0x1800588b7  mov     r10, r9
0x1800588ba  mov     r9, r8
0x1800588bd  mov     r8, rdx
0x1800588c0  mov     rdi, rcx
0x1800588c3  xor     esi, esi
0x1800588c5  mov     [rbp+20h+var_36], si
0x1800588c9  mov     [rbp+20h+var_48], 10h
0x1800588d0  lea     r11d, [rsi+2]
0x1800588d4  mov     [rbp+20h+var_44], r11d
0x1800588d8  lea     eax, [rsi+8]
0x1800588db  mov     [rbp+20h+var_40], ax
0x1800588df  mov     rax, cs:qword_18008CED0
0x1800588e6  mov     [rbp+20h+var_3E], rax
0x1800588ea  mov     [rbp+20h+var_94], 12h
0x1800588f1  lea     rax, [rbp+20h+var_48]
0x1800588f5  mov     [rbp+20h+var_90], rax
0x1800588f9  mov     [rbp+20h+var_98], 14h
0x180058900  mov     [rbp+20h+var_78.cBuffers], 1
0x180058907  lea     rax, [rbp+20h+var_98]
0x18005890b  mov     [rbp+20h+var_78.pBuffers], rax
0x18005890f  mov     [rbp+20h+var_78.ulVersion], esi
0x180058912  xorps   xmm0, xmm0
0x180058915  movups  xmmword ptr [rbp+20h+buf], xmm0
0x180058919  movups  [rbp+20h+var_58], xmm0
0x18005891d  mov     dword ptr [rbp+20h+buf+4], r11d
0x180058921  mov     dword ptr [rbp+20h+var_58+4], 11h
0x180058928  lea     rax, [rbp+20h+buf]
0x18005892c  mov     [rbp+20h+var_A0], rax
0x180058930  lea     rdx, [rbp+20h+var_A0]
0x180058934  lea     rcx, [rsp+120h+var_B8]
0x180058939  call    wil__scope_exit__lambda_e809bc703c2f031fb314c3909cbf4963___
0x18005893e  nop
0x18005893f  mov     [rbp+20h+var_88.cBuffers], r11d
0x180058943  lea     rax, [rbp+20h+buf]
0x180058947  mov     [rbp+20h+var_88.pBuffers], rax
0x18005894b  mov     [rbp+20h+var_88.ulVersion], esi
0x18005894e  mov     [rsp+120h+var_C0], esi
0x180058952  cmp     qword ptr [r8+18h], 7
0x180058957  jbe     short loc_18005895C
0x180058959  mov     r8, [r8]; pszTargetName
0x18005895c  mov     [rsp+120h+ptsExpiry], rsi; ptsExpiry
0x180058961  lea     rax, [rsp+120h+var_C0]
0x180058966  mov     [rsp+120h+pfContextAttr], rax; pfContextAttr
0x18005896b  lea     rax, [rbp+20h+var_88]
0x18005896f  mov     [rsp+120h+pOutput], rax; pOutput
0x180058974  mov     [rsp+120h+phNewContext], r9; phNewContext
0x180058979  mov     [rsp+120h+Reserved2], esi; Reserved2
0x18005897d  lea     rax, [rbp+20h+var_78]
0x180058981  mov     [rsp+120h+pInput], rax; pInput
0x180058986  mov     [rsp+120h+TargetDataRep], esi; TargetDataRep
0x18005898a  mov     [rsp+120h+Reserved1], esi; Reserved1
0x18005898e  xor     edx, edx; phContext
0x180058990  mov     r9d, 0C11Ch; fContextReq
0x180058996  mov     rcx, r10; phCredential
0x180058999  call    cs:__imp_InitializeSecurityContextW
0x1800589a0  nop     dword ptr [rax+rax+00h]
0x1800589a5  mov     ebx, eax
0x1800589a7  cmp     eax, 90312h
0x1800589ac  jz      short loc_1800589C2
0x1800589ae  xor     ecx, ecx
0x1800589b0  call    FileLogAllowEntry
0x1800589b5  test    al, al
0x1800589b7  jz      short loc_180058A22
0x1800589b9  lea     rcx, aInitialtlsInit; "InitialTls: InitializeSecurityContextW "...
0x1800589c0  jmp     short loc_180058A1A
0x1800589c2  mov     r8d, dword ptr [rbp+20h+buf]; len
0x1800589c6  test    r8d, r8d
0x1800589c9  jz      short loc_1800589ED
0x1800589cb  mov     rdx, [rbp+20h+buf+8]; buf
0x1800589cf  test    rdx, rdx
0x1800589d2  jz      short loc_1800589ED
0x1800589d4  xor     r9d, r9d; flags
0x1800589d7  mov     rcx, [rdi]; s
0x1800589da  call    cs:__imp_send
0x1800589e1  nop     dword ptr [rax+rax+00h]
0x1800589e6  inc     eax
0x1800589e8  cmp     eax, 1
0x1800589eb  ja      short loc_180058A22
0x1800589ed  call    cs:__imp_WSAGetLastError
0x1800589f4  nop     dword ptr [rax+rax+00h]
0x1800589f9  mov     ebx, eax
0x1800589fb  test    eax, eax
0x1800589fd  jle     short loc_180058A08
0x1800589ff  movzx   ebx, ax
0x180058a02  or      ebx, 80070000h
0x180058a08  xor     ecx, ecx
0x180058a0a  call    FileLogAllowEntry
0x180058a0f  test    al, al
0x180058a11  jz      short loc_180058A22
0x180058a13  lea     rcx, aInitialtlsSend; "InitialTls: Sending on socket failed wi"...
0x180058a1a  mov     edx, ebx
0x180058a1c  call    FileLogAdd
0x180058a21  nop
0x180058a22  cmp     [rsp+120h+var_B0], sil
0x180058a27  jz      short loc_180058A38
0x180058a29  mov     [rsp+120h+var_B0], sil
0x180058a2e  mov     rcx, [rsp+120h+var_B8]; struct _SecBuffer *
0x180058a33  call    ?FreeOutBuffers@@YAXQEAU_SecBuffer@@@Z; FreeOutBuffers(_SecBuffer * const)
0x180058a38  mov     eax, ebx
0x180058a3a  mov     rcx, [rbp+20h+var_30]
0x180058a3e  xor     rcx, rsp; StackCookie
0x180058a41  call    __security_check_cookie
0x180058a46  add     rsp, 108h
0x180058a4d  pop     rdi
0x180058a4e  pop     rsi
0x180058a4f  pop     rbx
0x180058a50  pop     rbp
0x180058a51  retn
```

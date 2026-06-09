# HttpClient::ExtractResponseBody(void *)

- ea: `0x1800534dc`
- end: `0x1800535fe`
- name: `?ExtractResponseBody@HttpClient@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180053e70`

## callees

- `0x180003110`
- `0x1800101e0`
- `0x180013eb4`
- `0x180014804`
- `0x180014884`
- `0x180019f58`
- `0x18003ffec`
- `0x1800404b0`
- `0x180052c98`
- `0x18005348c`
- `0x1800534dc`

## import_xrefs

- `WINHTTP!WinHttpReadData` at `0x18005356e`
- `WINHTTP!WinHttpReadData` at `0x18005356e`

## string_xrefs

- `0x1800535ec`: `onecore\base\flighting\common\httpclient\httpclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall HttpClient::ExtractResponseBody(__int64 a1, __int64 a2, void *a3)
{
  HttpClient *v5; // rcx
  const char *v6; // r9
  __int64 v7; // r8
  DWORD dwNumberOfBytesRead; // [rsp+20h] [rbp-60h] BYREF
  unsigned int v10[2]; // [rsp+28h] [rbp-58h] BYREF
  LPVOID lpBuffer[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v12; // [rsp+40h] [rbp-40h]
  _BYTE v13[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v10[1] = HIDWORD(a2);
  std::string::string(v13);
  v10[0] = 0;
  if ( HttpClient::ExtractHeaderAsDword(v5, a3, 5u, v10) >= 0 )
    std::string::reserve(v13, v10[0]);
  *(_OWORD *)lpBuffer = 0;
  v12 = 0;
  std::vector<char>::_Construct_n<>(lpBuffer);
  dwNumberOfBytesRead = 0;
  do
  {
    if ( !WinHttpReadData(a3, lpBuffer[0], 0x2000u, &dwNumberOfBytesRead) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x131,
        (unsigned int)"onecore\\base\\flighting\\common\\httpclient\\httpclient.cpp",
        v6);
    *((_BYTE *)lpBuffer[0] + dwNumberOfBytesRead) = 0;
    v7 = -1;
    do
      ++v7;
    while ( *((_BYTE *)lpBuffer[0] + v7) );
    std::string::_Append<char>(v13, lpBuffer[0]);
  }
  while ( dwNumberOfBytesRead );
  std::string::string(a2, v13);
  std::vector<unsigned char>::_Tidy(lpBuffer);
  std::string::_Tidy_deallocate(v13);
  return a2;
}

```

## disassembly

```asm
0x1800534dc  mov     [rsp-8+arg_0], rbx
0x1800534e1  mov     [rsp-8+arg_18], rdi
0x1800534e6  push    rbp
0x1800534e7  mov     rbp, rsp
0x1800534ea  sub     rsp, 80h
0x1800534f1  mov     rax, cs:__security_cookie
0x1800534f8  xor     rax, rsp
0x1800534fb  mov     [rbp+var_10], rax
0x1800534ff  mov     rdi, r8
0x180053502  mov     rbx, rdx
0x180053505  mov     qword ptr [rbp+var_58], rdx
0x180053509  lea     rcx, [rbp+var_30]
0x18005350d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180053512  nop
0x180053513  mov     [rbp+var_58], 0
0x18005351a  lea     r9, [rbp+var_58]; unsigned int *
0x18005351e  mov     r8d, 5; unsigned int
0x180053524  mov     rdx, rdi; void *
0x180053527  call    ?ExtractHeaderAsDword@HttpClient@@AEAAJPEAXKPEAK@Z; HttpClient::ExtractHeaderAsDword(void *,ulong,ulong *)
0x18005352c  test    eax, eax
0x18005352e  js      short loc_18005353C
0x180053530  mov     edx, [rbp+var_58]
0x180053533  lea     rcx, [rbp+var_30]
0x180053537  call    ?reserve@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::string::reserve(unsigned __int64)
0x18005353c  xorps   xmm0, xmm0
0x18005353f  movdqu  xmmword ptr [rbp+lpBuffer], xmm0
0x180053544  mov     [rbp+var_40], 0
0x18005354c  lea     rcx, [rbp+lpBuffer]
0x180053550  call    ??$_Construct_n@$$V@?$vector@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::vector<char>::_Construct_n<>(unsigned __int64)
0x180053555  nop
0x180053556  mov     [rbp+dwNumberOfBytesRead], 0
0x18005355d  lea     r9, [rbp+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x180053561  mov     r8d, 2000h; dwNumberOfBytesToRead
0x180053567  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x18005356b  mov     rcx, rdi; hRequest
0x18005356e  call    cs:__imp_WinHttpReadData
0x180053574  mov     rcx, [rbp+8]; this
0x180053578  test    eax, eax
0x18005357a  jz      short loc_1800535EC
0x18005357c  mov     ecx, [rbp+dwNumberOfBytesRead]
0x18005357f  mov     rax, [rbp+lpBuffer]
0x180053583  mov     byte ptr [rcx+rax], 0
0x180053587  mov     rdx, [rbp+lpBuffer]
0x18005358b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005358f  inc     r8
0x180053592  cmp     byte ptr [rdx+r8], 0
0x180053597  jnz     short loc_18005358F
0x180053599  lea     rcx, [rbp+var_30]
0x18005359d  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800535a2  cmp     [rbp+dwNumberOfBytesRead], 0
0x1800535a6  ja      short loc_18005355D
0x1800535a8  lea     rdx, [rbp+var_30]
0x1800535ac  mov     rcx, rbx
0x1800535af  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x1800535b4  nop
0x1800535b5  lea     rcx, [rbp+lpBuffer]
0x1800535b9  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800535be  nop
0x1800535bf  lea     rcx, [rbp+var_30]
0x1800535c3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800535c8  mov     rax, rbx
0x1800535cb  mov     rcx, [rbp+var_10]
0x1800535cf  xor     rcx, rsp; StackCookie
0x1800535d2  call    __security_check_cookie
0x1800535d7  lea     r11, [rsp+80h+var_s0]
0x1800535df  mov     rbx, [r11+10h]
0x1800535e3  mov     rdi, [r11+28h]
0x1800535e7  mov     rsp, r11
0x1800535ea  pop     rbp
0x1800535eb  retn
0x1800535ec  lea     r8, aOnecoreBaseFli_31; "onecore\\base\\flighting\\common\\httpc"...
0x1800535f3  mov     edx, 131h; void *
0x1800535f8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```

# EnumChannelCommand::Execute(void)

- ea: `0x140025890`
- end: `0x140025ae5`
- name: `?Execute@EnumChannelCommand@@UEAAXXZ`
- size: `597`
- prototype: `void __fastcall(EnumChannelCommand *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x14000a574`
- `0x14000cabc`
- `0x14000d900`
- `0x140010450`
- `0x14001a44c`
- `0x14001acfc`
- `0x14001b084`
- `0x1400202c4`
- `0x140021b00`
- `0x140022cec`
- `0x140025700`
- `0x140025890`
- `0x140031810`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__putws` at `0x14002596e`
- `api-ms-win-crt-private-l1-1-0!_o__putws` at `0x14002596e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025a5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025a5d`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtOpenChannelEnum` at `0x1400258b5`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtOpenChannelEnum` at `0x1400258b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EnumChannelCommand::Execute(EVT_HANDLE *this)
{
  EVT_HANDLE v1; // rbx
  unsigned int NextChannelPath; // eax
  __int64 v3; // r9
  unsigned int v4; // edi
  wchar_t *v5; // rbx
  wchar_t *v6; // rsi
  const wchar_t *v7; // rcx
  DWORD LastError; // ebx
  const char *v9; // [rsp+20h] [rbp-59h]
  wchar_t *Buffer[2]; // [rsp+40h] [rbp-39h] BYREF
  wchar_t *v11; // [rsp+50h] [rbp-29h]
  EVT_HANDLE v12; // [rsp+58h] [rbp-21h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+60h] [rbp-19h] BYREF
  WCHAR ChannelPathBuffer[8]; // [rsp+88h] [rbp+Fh] BYREF
  __m128i si128; // [rsp+98h] [rbp+1Fh]

  v1 = EvtOpenChannelEnum(this[3], 0);
  v12 = v1;
  if ( !v1 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a8430618997d38340c5c5ca52b1e08d9_Traceguids, LastError);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, v9, 54, 0x29u, 0);
    throw (EvtException *)pExceptionObject;
  }
  *(_OWORD *)ChannelPathBuffer = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  ChannelPathBuffer[0] = 0;
  *(_OWORD *)Buffer = 0;
  v11 = 0;
  while ( 1 )
  {
    NextChannelPath = GetNextChannelPath(v1, ChannelPathBuffer);
    v4 = NextChannelPath;
    if ( NextChannelPath == 259 )
      break;
    if ( NextChannelPath )
      goto LABEL_9;
    if ( Buffer[1] == v11 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(Buffer, Buffer[1], ChannelPathBuffer);
    }
    else
    {
      std::wstring::wstring(Buffer[1], ChannelPathBuffer);
      Buffer[1] += 16;
    }
  }
  v4 = 0;
LABEL_9:
  LOBYTE(v3) = 0;
  std::_Sort_unchecked<std::wstring *,std::less<void>>(
    Buffer[0],
    Buffer[1],
    ((char *)Buffer[1] - (char *)Buffer[0]) >> 5,
    v3);
  v5 = Buffer[0];
  v6 = Buffer[1];
  if ( Buffer[0] != Buffer[1] )
  {
    do
    {
      if ( *((_QWORD *)v5 + 3) <= 7u )
        v7 = v5;
      else
        v7 = *(const wchar_t **)v5;
      _putws(v7);
      v5 += 16;
    }
    while ( v5 != v6 );
    v6 = Buffer[1];
    v5 = Buffer[0];
  }
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a8430618997d38340c5c5ca52b1e08d9_Traceguids, v4);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v4, 0, 0, v9, 88, 0x2Au, 0);
    throw (EvtException *)pExceptionObject;
  }
  if ( v5 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v5, v6);
    std::_Deallocate<16>(Buffer[0], ((char *)v11 - (char *)Buffer[0]) & 0xFFFFFFFFFFFFFFE0uLL);
    *(_OWORD *)Buffer = 0;
    v11 = 0;
  }
  std::wstring::_Tidy_deallocate(ChannelPathBuffer);
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v12);
}

```

## disassembly

```asm
0x140025890  push    rbp
0x140025892  push    rbx
0x140025893  push    rsi
0x140025894  push    rdi
0x140025895  lea     rbp, [rsp-3Fh]
0x14002589a  sub     rsp, 0B8h
0x1400258a1  mov     rax, cs:__security_cookie
0x1400258a8  xor     rax, rsp
0x1400258ab  mov     [rbp+57h+var_28], rax
0x1400258af  xor     edx, edx; Flags
0x1400258b1  mov     rcx, [rcx+18h]; Session
0x1400258b5  call    cs:__imp_EvtOpenChannelEnum
0x1400258bb  mov     rbx, rax
0x1400258be  mov     [rbp+57h+var_78], rax
0x1400258c2  test    rax, rax
0x1400258c5  jz      loc_140025A5D
0x1400258cb  xorps   xmm0, xmm0
0x1400258ce  movups  xmmword ptr [rbp+57h+ChannelPathBuffer], xmm0
0x1400258d2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400258da  movdqu  [rbp+57h+var_38], xmm1
0x1400258df  xor     ecx, ecx
0x1400258e1  mov     [rbp+57h+ChannelPathBuffer], cx
0x1400258e5  movdqu  xmmword ptr [rbp+57h+Buffer], xmm0
0x1400258ea  mov     [rbp+57h+var_80], rcx
0x1400258ee  lea     rdx, [rbp+57h+ChannelPathBuffer]; ChannelPathBuffer
0x1400258f2  mov     rcx, rbx; ChannelEnum
0x1400258f5  call    GetNextChannelPath
0x1400258fa  mov     edi, eax
0x1400258fc  cmp     eax, 103h
0x140025901  jz      short loc_140025936
0x140025903  test    eax, eax
0x140025905  jnz     short loc_140025938
0x140025907  mov     rax, [rbp+57h+Buffer+8]
0x14002590b  cmp     rax, [rbp+57h+var_80]
0x14002590f  jz      short loc_140025924
0x140025911  lea     rdx, [rbp+57h+ChannelPathBuffer]
0x140025915  mov     rcx, rax
0x140025918  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14002591d  add     [rbp+57h+Buffer+8], 20h ; ' '
0x140025922  jmp     short loc_1400258EE
0x140025924  lea     r8, [rbp+57h+ChannelPathBuffer]
0x140025928  mov     rdx, rax
0x14002592b  lea     rcx, [rbp+57h+Buffer]
0x14002592f  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x140025934  jmp     short loc_1400258EE
0x140025936  xor     edi, edi
0x140025938  mov     rdx, [rbp+57h+Buffer+8]
0x14002593c  mov     rcx, [rbp+57h+Buffer]
0x140025940  xor     r9b, r9b
0x140025943  mov     r8, rdx
0x140025946  sub     r8, rcx
0x140025949  sar     r8, 5
0x14002594d  call    ??$_Sort_unchecked@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@X@2@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0_JU?$less@X@0@@Z; std::_Sort_unchecked<std::wstring *,std::less<void>>(std::wstring *,std::wstring *,__int64,std::less<void>)
0x140025952  mov     rbx, [rbp+57h+Buffer]
0x140025956  mov     rsi, [rbp+57h+Buffer+8]
0x14002595a  cmp     rbx, rsi
0x14002595d  jz      short loc_140025985
0x14002595f  cmp     qword ptr [rbx+18h], 7
0x140025964  jbe     short loc_14002596B
0x140025966  mov     rcx, [rbx]
0x140025969  jmp     short loc_14002596E
0x14002596b  mov     rcx, rbx; Buffer
0x14002596e  call    cs:__imp__putws
0x140025974  add     rbx, 20h ; ' '
0x140025978  cmp     rbx, rsi
0x14002597b  jnz     short loc_14002595F
0x14002597d  mov     rsi, [rbp+57h+Buffer+8]
0x140025981  mov     rbx, [rbp+57h+Buffer]
0x140025985  test    edi, edi
0x140025987  jz      short loc_1400259FE
0x140025989  lea     rax, WPP_GLOBAL_Control
0x140025990  mov     rcx, cs:WPP_GLOBAL_Control
0x140025997  cmp     rcx, rax
0x14002599a  jz      short loc_1400259C3
0x14002599c  test    dword ptr [rcx+1Ch], 400000h
0x1400259a3  jz      short loc_1400259C3
0x1400259a5  cmp     byte ptr [rcx+19h], 2
0x1400259a9  jb      short loc_1400259C3
0x1400259ab  mov     edx, 0Bh
0x1400259b0  mov     r9d, edi
0x1400259b3  lea     r8, WPP_a8430618997d38340c5c5ca52b1e08d9_Traceguids
0x1400259ba  mov     rcx, [rcx+10h]
0x1400259be  call    WPP_SF_d
0x1400259c3  mov     [rsp+0D0h+Src], 0; Src
0x1400259cc  mov     [rsp+0D0h+var_A0], 2Ah ; '*'; unsigned int
0x1400259d4  mov     [rsp+0D0h+var_A8], 58h ; 'X'; int
0x1400259dc  xor     r9d, r9d; unsigned int
0x1400259df  xor     r8d, r8d; unsigned int
0x1400259e2  mov     edx, edi; unsigned int
0x1400259e4  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400259e8  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400259ed  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400259f4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400259f8  call    _CxxThrowException_0
0x1400259fe  test    rbx, rbx
0x140025a01  jz      short loc_140025A32
0x140025a03  mov     rdx, rsi
0x140025a06  mov     rcx, rbx
0x140025a09  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x140025a0e  mov     rcx, [rbp+57h+Buffer]
0x140025a12  mov     rdx, [rbp+57h+var_80]
0x140025a16  sub     rdx, rcx
0x140025a19  and     rdx, 0FFFFFFFFFFFFFFE0h
0x140025a1d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140025a22  xorps   xmm0, xmm0
0x140025a25  movdqu  xmmword ptr [rbp+57h+Buffer], xmm0
0x140025a2a  mov     [rbp+57h+var_80], 0
0x140025a32  lea     rcx, [rbp+57h+ChannelPathBuffer]
0x140025a36  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140025a3b  nop
0x140025a3c  lea     rcx, [rbp+57h+var_78]
0x140025a40  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>(void)
0x140025a45  mov     rcx, [rbp+57h+var_28]
0x140025a49  xor     rcx, rsp; StackCookie
0x140025a4c  call    __security_check_cookie
0x140025a51  add     rsp, 0B8h
0x140025a58  pop     rdi
0x140025a59  pop     rsi
0x140025a5a  pop     rbx
0x140025a5b  pop     rbp
0x140025a5c  retn
0x140025a5d  call    cs:__imp_GetLastError
0x140025a63  nop
0x140025a64  mov     ebx, eax
0x140025a66  mov     eax, 507h
0x140025a6b  test    ebx, ebx
0x140025a6d  cmovz   ebx, eax
0x140025a70  lea     rax, WPP_GLOBAL_Control
0x140025a77  mov     rcx, cs:WPP_GLOBAL_Control
0x140025a7e  cmp     rcx, rax
0x140025a81  jz      short loc_140025AAA
0x140025a83  test    dword ptr [rcx+1Ch], 400000h
0x140025a8a  jz      short loc_140025AAA
0x140025a8c  cmp     byte ptr [rcx+19h], 2
0x140025a90  jb      short loc_140025AAA
0x140025a92  mov     edx, 0Ah
0x140025a97  mov     r9d, ebx
0x140025a9a  lea     r8, WPP_a8430618997d38340c5c5ca52b1e08d9_Traceguids
0x140025aa1  mov     rcx, [rcx+10h]
0x140025aa5  call    WPP_SF_d
0x140025aaa  mov     [rsp+0D0h+Src], 0; Src
0x140025ab3  mov     [rsp+0D0h+var_A0], 29h ; ')'; unsigned int
0x140025abb  mov     [rsp+0D0h+var_A8], 36h ; '6'; int
0x140025ac3  xor     r9d, r9d; unsigned int
0x140025ac6  xor     r8d, r8d; unsigned int
0x140025ac9  mov     edx, ebx; unsigned int
0x140025acb  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140025acf  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140025ad4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140025adb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140025adf  call    _CxxThrowException_0
```

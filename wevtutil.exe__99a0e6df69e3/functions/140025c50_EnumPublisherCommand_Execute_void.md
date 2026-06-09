# EnumPublisherCommand::Execute(void)

- ea: `0x140025c50`
- end: `0x140025f20`
- name: `?Execute@EnumPublisherCommand@@UEAAXXZ`
- size: `720`
- prototype: `void __fastcall(EnumPublisherCommand *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x14000a574`
- `0x14000cabc`
- `0x14000d900`
- `0x140010450`
- `0x14001a774`
- `0x14001acfc`
- `0x14001b084`
- `0x1400202c4`
- `0x140021b00`
- `0x140022cec`
- `0x140025700`
- `0x140025c50`
- `0x140031810`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__putws` at `0x140025da9`
- `api-ms-win-crt-private-l1-1-0!_o__putws` at `0x140025da9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025d1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025e98`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtNextPublisherId` at `0x140025cd7`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtNextPublisherId` at `0x140025d12`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtNextPublisherId` at `0x140025cd7`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtNextPublisherId` at `0x140025d12`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtOpenPublisherEnum` at `0x140025c75`
- `ext-ms-win-wevtapi-eventlog-l1-1-3!EvtOpenPublisherEnum` at `0x140025c75`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EnumPublisherCommand::Execute(EVT_HANDLE *this)
{
  EVT_HANDLE v1; // rbx
  WCHAR *v2; // r8
  DWORD v3; // edi
  __int64 v4; // r9
  WCHAR *v5; // r8
  wchar_t *v6; // rbx
  wchar_t *v7; // rsi
  const wchar_t *v8; // rcx
  DWORD LastError; // ebx
  const char *v10; // [rsp+20h] [rbp-69h]
  DWORD PublisherIdBufferUsed; // [rsp+40h] [rbp-49h] BYREF
  wchar_t *Buffer[2]; // [rsp+48h] [rbp-41h] BYREF
  wchar_t *v13; // [rsp+58h] [rbp-31h]
  EVT_HANDLE v14; // [rsp+60h] [rbp-29h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+68h] [rbp-21h] BYREF
  LPWSTR PublisherIdBuffer[2]; // [rsp+90h] [rbp+7h] BYREF
  DWORD PublisherIdBufferSize[4]; // [rsp+A0h] [rbp+17h]

  v1 = EvtOpenPublisherEnum(this[3], 0);
  v14 = v1;
  if ( !v1 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_726bac6a6eb33d6ca64d0eb1ac9e1aa9_Traceguids, LastError);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, v10, 23, 0x16u, 0);
    throw (EvtException *)pExceptionObject;
  }
  *(_OWORD *)PublisherIdBuffer = 0;
  *(__m128i *)PublisherIdBufferSize = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(PublisherIdBuffer[0]) = 0;
  *(_OWORD *)Buffer = 0;
  v13 = 0;
  std::wstring::resize(PublisherIdBuffer, 512);
  while ( 1 )
  {
    PublisherIdBufferUsed = PublisherIdBufferSize[0];
    v2 = (WCHAR *)PublisherIdBuffer;
    if ( *(_QWORD *)&PublisherIdBufferSize[2] > 7u )
      v2 = PublisherIdBuffer[0];
    if ( EvtNextPublisherId(v1, PublisherIdBufferSize[0], v2, &PublisherIdBufferUsed) )
      goto LABEL_13;
    v3 = GetLastError();
    if ( v3 == 122 )
    {
      std::wstring::resize(PublisherIdBuffer, PublisherIdBufferUsed);
      v5 = (WCHAR *)PublisherIdBuffer;
      if ( *(_QWORD *)&PublisherIdBufferSize[2] > 7u )
        v5 = PublisherIdBuffer[0];
      if ( EvtNextPublisherId(v1, PublisherIdBufferUsed, v5, &PublisherIdBufferUsed) )
        goto LABEL_13;
      v3 = GetLastError();
    }
    if ( v3 == 259 )
      break;
    if ( v3 )
      goto LABEL_17;
LABEL_13:
    std::wstring::resize(PublisherIdBuffer, PublisherIdBufferUsed);
    if ( Buffer[1] == v13 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(Buffer, Buffer[1], PublisherIdBuffer);
    }
    else
    {
      std::wstring::wstring(Buffer[1], PublisherIdBuffer);
      Buffer[1] += 16;
    }
  }
  v3 = 0;
LABEL_17:
  LOBYTE(v4) = 0;
  std::_Sort_unchecked<std::wstring *,std::less<void>>(
    Buffer[0],
    Buffer[1],
    ((char *)Buffer[1] - (char *)Buffer[0]) >> 5,
    v4);
  v6 = Buffer[0];
  v7 = Buffer[1];
  if ( Buffer[0] != Buffer[1] )
  {
    do
    {
      if ( *((_QWORD *)v6 + 3) <= 7u )
        v8 = v6;
      else
        v8 = *(const wchar_t **)v6;
      _putws(v8);
      v6 += 16;
    }
    while ( v6 != v7 );
    v7 = Buffer[1];
    v6 = Buffer[0];
  }
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_726bac6a6eb33d6ca64d0eb1ac9e1aa9_Traceguids, v3);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v3, 0, 0, v10, 75, 0x17u, 0);
    throw (EvtException *)pExceptionObject;
  }
  if ( v6 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v6, v7);
    std::_Deallocate<16>(Buffer[0], ((char *)v13 - (char *)Buffer[0]) & 0xFFFFFFFFFFFFFFE0uLL);
    *(_OWORD *)Buffer = 0;
    v13 = 0;
  }
  std::wstring::_Tidy_deallocate(PublisherIdBuffer);
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(&v14);
}

```

## disassembly

```asm
0x140025c50  push    rbp
0x140025c52  push    rbx
0x140025c53  push    rsi
0x140025c54  push    rdi
0x140025c55  lea     rbp, [rsp-3Fh]
0x140025c5a  sub     rsp, 0C8h
0x140025c61  mov     rax, cs:__security_cookie
0x140025c68  xor     rax, rsp
0x140025c6b  mov     [rbp+57h+var_30], rax
0x140025c6f  xor     edx, edx; Flags
0x140025c71  mov     rcx, [rcx+18h]; Session
0x140025c75  call    cs:__imp_EvtOpenPublisherEnum
0x140025c7b  mov     rbx, rax
0x140025c7e  mov     [rbp+57h+var_80], rax
0x140025c82  test    rax, rax
0x140025c85  jz      loc_140025E98
0x140025c8b  xorps   xmm0, xmm0
0x140025c8e  movups  xmmword ptr [rbp+57h+PublisherIdBuffer], xmm0
0x140025c92  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140025c9a  movdqu  xmmword ptr [rbp+57h+PublisherIdBufferSize], xmm1
0x140025c9f  xor     ecx, ecx
0x140025ca1  mov     word ptr [rbp+57h+PublisherIdBuffer], cx
0x140025ca5  movdqu  xmmword ptr [rbp+57h+Buffer], xmm0
0x140025caa  mov     [rbp+57h+var_88], rcx
0x140025cae  mov     edx, 200h
0x140025cb3  lea     rcx, [rbp+57h+PublisherIdBuffer]
0x140025cb7  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x140025cbc  mov     edx, [rbp+57h+PublisherIdBufferSize]; PublisherIdBufferSize
0x140025cbf  mov     [rbp+57h+PublisherIdBufferUsed], edx
0x140025cc2  lea     r8, [rbp+57h+PublisherIdBuffer]
0x140025cc6  cmp     qword ptr [rbp+57h+PublisherIdBufferSize+8], 7
0x140025ccb  cmova   r8, [rbp+57h+PublisherIdBuffer]; PublisherIdBuffer
0x140025cd0  lea     r9, [rbp+57h+PublisherIdBufferUsed]; PublisherIdBufferUsed
0x140025cd4  mov     rcx, rbx; PublisherEnum
0x140025cd7  call    cs:__imp_EvtNextPublisherId
0x140025cdd  test    eax, eax
0x140025cdf  jnz     short loc_140025D30
0x140025ce1  call    cs:__imp_GetLastError
0x140025ce7  mov     edi, eax
0x140025ce9  cmp     eax, 7Ah ; 'z'
0x140025cec  jnz     short loc_140025D24
0x140025cee  mov     edx, [rbp+57h+PublisherIdBufferUsed]
0x140025cf1  lea     rcx, [rbp+57h+PublisherIdBuffer]
0x140025cf5  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x140025cfa  lea     r8, [rbp+57h+PublisherIdBuffer]
0x140025cfe  cmp     qword ptr [rbp+57h+PublisherIdBufferSize+8], 7
0x140025d03  cmova   r8, [rbp+57h+PublisherIdBuffer]; PublisherIdBuffer
0x140025d08  lea     r9, [rbp+57h+PublisherIdBufferUsed]; PublisherIdBufferUsed
0x140025d0c  mov     edx, [rbp+57h+PublisherIdBufferUsed]; PublisherIdBufferSize
0x140025d0f  mov     rcx, rbx; PublisherEnum
0x140025d12  call    cs:__imp_EvtNextPublisherId
0x140025d18  test    eax, eax
0x140025d1a  jnz     short loc_140025D30
0x140025d1c  call    cs:__imp_GetLastError
0x140025d22  mov     edi, eax
0x140025d24  cmp     edi, 103h
0x140025d2a  jz      short loc_140025D71
0x140025d2c  test    edi, edi
0x140025d2e  jnz     short loc_140025D73
0x140025d30  mov     edx, [rbp+57h+PublisherIdBufferUsed]
0x140025d33  lea     rcx, [rbp+57h+PublisherIdBuffer]
0x140025d37  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x140025d3c  mov     rax, [rbp+57h+Buffer+8]
0x140025d40  cmp     rax, [rbp+57h+var_88]
0x140025d44  jz      short loc_140025D5C
0x140025d46  lea     rdx, [rbp+57h+PublisherIdBuffer]
0x140025d4a  mov     rcx, rax
0x140025d4d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140025d52  add     [rbp+57h+Buffer+8], 20h ; ' '
0x140025d57  jmp     loc_140025CBC
0x140025d5c  lea     r8, [rbp+57h+PublisherIdBuffer]
0x140025d60  mov     rdx, rax
0x140025d63  lea     rcx, [rbp+57h+Buffer]
0x140025d67  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x140025d6c  jmp     loc_140025CBC
0x140025d71  xor     edi, edi
0x140025d73  mov     rdx, [rbp+57h+Buffer+8]
0x140025d77  mov     rcx, [rbp+57h+Buffer]
0x140025d7b  xor     r9b, r9b
0x140025d7e  mov     r8, rdx
0x140025d81  sub     r8, rcx
0x140025d84  sar     r8, 5
0x140025d88  call    ??$_Sort_unchecked@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@X@2@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0_JU?$less@X@0@@Z; std::_Sort_unchecked<std::wstring *,std::less<void>>(std::wstring *,std::wstring *,__int64,std::less<void>)
0x140025d8d  mov     rbx, [rbp+57h+Buffer]
0x140025d91  mov     rsi, [rbp+57h+Buffer+8]
0x140025d95  cmp     rbx, rsi
0x140025d98  jz      short loc_140025DC0
0x140025d9a  cmp     qword ptr [rbx+18h], 7
0x140025d9f  jbe     short loc_140025DA6
0x140025da1  mov     rcx, [rbx]
0x140025da4  jmp     short loc_140025DA9
0x140025da6  mov     rcx, rbx; Buffer
0x140025da9  call    cs:__imp__putws
0x140025daf  add     rbx, 20h ; ' '
0x140025db3  cmp     rbx, rsi
0x140025db6  jnz     short loc_140025D9A
0x140025db8  mov     rsi, [rbp+57h+Buffer+8]
0x140025dbc  mov     rbx, [rbp+57h+Buffer]
0x140025dc0  test    edi, edi
0x140025dc2  jz      short loc_140025E39
0x140025dc4  lea     rax, WPP_GLOBAL_Control
0x140025dcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140025dd2  cmp     rcx, rax
0x140025dd5  jz      short loc_140025DFE
0x140025dd7  test    dword ptr [rcx+1Ch], 400000h
0x140025dde  jz      short loc_140025DFE
0x140025de0  cmp     byte ptr [rcx+19h], 2
0x140025de4  jb      short loc_140025DFE
0x140025de6  mov     edx, 0Bh
0x140025deb  mov     r9d, edi
0x140025dee  lea     r8, WPP_726bac6a6eb33d6ca64d0eb1ac9e1aa9_Traceguids
0x140025df5  mov     rcx, [rcx+10h]
0x140025df9  call    WPP_SF_d
0x140025dfe  mov     [rsp+0E0h+Src], 0; Src
0x140025e07  mov     [rsp+0E0h+var_B0], 17h; unsigned int
0x140025e0f  mov     [rsp+0E0h+var_B8], 4Bh ; 'K'; int
0x140025e17  xor     r9d, r9d; unsigned int
0x140025e1a  xor     r8d, r8d; unsigned int
0x140025e1d  mov     edx, edi; unsigned int
0x140025e1f  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140025e23  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140025e28  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140025e2f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140025e33  call    _CxxThrowException_0
0x140025e39  test    rbx, rbx
0x140025e3c  jz      short loc_140025E6D
0x140025e3e  mov     rdx, rsi
0x140025e41  mov     rcx, rbx
0x140025e44  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x140025e49  mov     rcx, [rbp+57h+Buffer]
0x140025e4d  mov     rdx, [rbp+57h+var_88]
0x140025e51  sub     rdx, rcx
0x140025e54  and     rdx, 0FFFFFFFFFFFFFFE0h
0x140025e58  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140025e5d  xorps   xmm0, xmm0
0x140025e60  movdqu  xmmword ptr [rbp+57h+Buffer], xmm0
0x140025e65  mov     [rbp+57h+var_88], 0
0x140025e6d  lea     rcx, [rbp+57h+PublisherIdBuffer]
0x140025e71  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140025e76  nop
0x140025e77  lea     rcx, [rbp+57h+var_80]
0x140025e7b  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>(void)
0x140025e80  mov     rcx, [rbp+57h+var_30]
0x140025e84  xor     rcx, rsp; StackCookie
0x140025e87  call    __security_check_cookie
0x140025e8c  add     rsp, 0C8h
0x140025e93  pop     rdi
0x140025e94  pop     rsi
0x140025e95  pop     rbx
0x140025e96  pop     rbp
0x140025e97  retn
0x140025e98  call    cs:__imp_GetLastError
0x140025e9e  nop
0x140025e9f  mov     ebx, eax
0x140025ea1  mov     eax, 507h
0x140025ea6  test    ebx, ebx
0x140025ea8  cmovz   ebx, eax
0x140025eab  lea     rax, WPP_GLOBAL_Control
0x140025eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140025eb9  cmp     rcx, rax
0x140025ebc  jz      short loc_140025EE5
0x140025ebe  test    dword ptr [rcx+1Ch], 400000h
0x140025ec5  jz      short loc_140025EE5
0x140025ec7  cmp     byte ptr [rcx+19h], 2
0x140025ecb  jb      short loc_140025EE5
0x140025ecd  mov     edx, 0Ah
0x140025ed2  mov     r9d, ebx
0x140025ed5  lea     r8, WPP_726bac6a6eb33d6ca64d0eb1ac9e1aa9_Traceguids
0x140025edc  mov     rcx, [rcx+10h]
0x140025ee0  call    WPP_SF_d
0x140025ee5  mov     [rsp+0E0h+Src], 0; Src
0x140025eee  mov     [rsp+0E0h+var_B0], 16h; unsigned int
0x140025ef6  mov     [rsp+0E0h+var_B8], 17h; int
0x140025efe  xor     r9d, r9d; unsigned int
0x140025f01  xor     r8d, r8d; unsigned int
0x140025f04  mov     edx, ebx; unsigned int
0x140025f06  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140025f0a  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140025f0f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140025f16  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140025f1a  call    _CxxThrowException_0
```

# CWerService::SvcCollectETWLogs(_WERSVC_MSG *,_WERSVC_MSG *)

- ea: `0x180018c5c`
- end: `0x180018e8a`
- name: `?SvcCollectETWLogs@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z`
- size: `558`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct _WERSVC_MSG *, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180014fa4`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x180004a44`
- `0x18000fea4`
- `0x1800101dc`
- `0x180011648`
- `0x180017f88`
- `0x180018c5c`
- `0x180031558`
- `0x180031610`
- `0x180031a48`
- `0x180031d14`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018e0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018e0f`
- `wer!WerpGetPathOfWERTempDirectory` at `0x180018d0e`
- `wer!WerpGetPathOfWERTempDirectory` at `0x180018d0e`

## pseudocode

```c
__int64 __fastcall CWerService::SvcCollectETWLogs(
        struct _RTL_CRITICAL_SECTION *this,
        struct _WERSVC_MSG *a2,
        struct _WERSVC_MSG *a3)
{
  const wchar_t *v5; // rdi
  int PathOfWERTempDirectory; // ebx
  __int64 v7; // r8
  int v8; // edi
  const wchar_t *v9; // rdx
  int v10; // eax
  CWerService *v11; // rcx
  HANDLE hObject; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t *v14[2]; // [rsp+28h] [rbp-D8h] BYREF
  _WORD v15[12]; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v16[3]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v17[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v18[8]; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v19; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v20[528]; // [rsp+B0h] [rbp-50h] BYREF

  *((_WORD *)a2 + 283) = 0;
  v5 = (const wchar_t *)((char *)a2 + 48);
  v14[0] = v15;
  v14[1] = v15;
  v15[0] = 0;
  hObject = 0;
  v16[0] = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v16[1] = v16[0];
  v16[2] = v16[0];
  v17[0] = v18;
  v17[1] = v18;
  v18[0] = 0;
  v19 = 0;
  if ( a2 == (struct _WERSVC_MSG *)-48LL || !*v5 )
  {
    PathOfWERTempDirectory = -2147024809;
  }
  else
  {
    PathOfWERTempDirectory = WerpGetPathOfWERTempDirectory(v20, 260);
    if ( PathOfWERTempDirectory >= 0 )
    {
      PathOfWERTempDirectory = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                                 v14,
                                 L"%ws\\%ws",
                                 v20,
                                 v5);
      if ( PathOfWERTempDirectory >= 0 )
      {
        PathOfWERTempDirectory = UtilVerifyAndLockDirectory(v14[0], &hObject);
        if ( PathOfWERTempDirectory >= 0 )
        {
          PathOfWERTempDirectory = UtilParseGuidString(v5, &v19);
          if ( PathOfWERTempDirectory >= 0 )
          {
            v7 = -1;
            do
              ++v7;
            while ( v5[v7] );
            if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                    v17,
                                    v5) )
            {
              PathOfWERTempDirectory = CEtwTraceManager::AddSessionsFromRegistry(
                                         (CEtwTraceManager *)v16,
                                         L"Software\\Microsoft\\Windows\\Windows Error Reporting\\EtwSessions");
              v8 = CEtwTraceManager::AddSessionsFromRegistry(
                     (CEtwTraceManager *)v16,
                     L"Software\\Microsoft\\Windows\\Windows Error Reporting\\DynamicEtwSessions");
              v10 = CEtwTraceManager::AddWprcInstancesFromRegistry((CEtwTraceManager *)v16, v9);
              if ( PathOfWERTempDirectory >= 0 || v8 >= 0 || v10 >= 0 )
                PathOfWERTempDirectory = CEtwTraceManager::FlushAllSessions((CEtwTraceManager *)v16, v14[0], this + 1);
              *((_DWORD *)a3 + 142) = 0;
              CWerService::SnapHostOrGuestOneTrace(v11, v14[0], (unsigned int *)a3 + 142);
            }
            else
            {
              PathOfWERTempDirectory = -2147024882;
            }
          }
        }
      }
    }
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  *((_DWORD *)a3 + 11) = PathOfWERTempDirectory;
  *((_DWORD *)a3 + 10) = ((PathOfWERTempDirectory >> 31) & 1) - 268369920;
  *((_DWORD *)a3 + 142) += (__int64)(*((_QWORD *)&v16[0] + 1) - *(_QWORD *)&v16[0]) >> 3;
  CEtwTraceManager::~CEtwTraceManager((CEtwTraceManager *)v16);
  if ( v14[0] != v15 )
    operator delete(v14[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)PathOfWERTempDirectory;
}

```

## disassembly

```asm
0x180018c5c  mov     [rsp-8+arg_18], rbx
0x180018c61  push    rbp
0x180018c62  push    rsi
0x180018c63  push    rdi
0x180018c64  push    r14
0x180018c66  push    r15
0x180018c68  lea     rbp, [rsp-1D0h]
0x180018c70  sub     rsp, 2D0h
0x180018c77  mov     rax, cs:__security_cookie
0x180018c7e  xor     rax, rsp
0x180018c81  mov     [rbp+1F0h+var_30], rax
0x180018c88  mov     rsi, r8
0x180018c8b  mov     r14, rcx
0x180018c8e  xor     r15d, r15d
0x180018c91  mov     [rdx+236h], r15w
0x180018c99  lea     rdi, [rdx+30h]
0x180018c9d  lea     rax, [rsp+2F0h+var_2B8]
0x180018ca2  mov     [rsp+2F0h+var_2C8], rax
0x180018ca7  lea     rax, [rsp+2F0h+var_2B8]
0x180018cac  mov     [rsp+2F0h+var_2C0], rax
0x180018cb1  mov     [rsp+2F0h+var_2B8], r15w
0x180018cb7  mov     [rsp+2F0h+hObject], r15
0x180018cbc  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180018cc4  movdqa  [rsp+2F0h+var_2A0], xmm0
0x180018cca  movdqa  [rsp+2F0h+var_290], xmm0
0x180018cd0  movdqa  [rsp+2F0h+var_280], xmm0
0x180018cd6  lea     rax, [rbp+1F0h+var_260]
0x180018cda  mov     [rbp+1F0h+var_270], rax
0x180018cde  lea     rax, [rbp+1F0h+var_260]
0x180018ce2  mov     [rbp+1F0h+var_268], rax
0x180018ce6  mov     [rbp+1F0h+var_260], r15w
0x180018ceb  xorps   xmm0, xmm0
0x180018cee  movups  xmmword ptr [rbp+1F0h+var_250.Data1], xmm0
0x180018cf2  test    rdi, rdi
0x180018cf5  jz      loc_180018DFB
0x180018cfb  cmp     [rdi], r15w
0x180018cff  jz      loc_180018DFB
0x180018d05  mov     edx, 104h
0x180018d0a  lea     rcx, [rbp+1F0h+var_240]
0x180018d0e  call    cs:__imp_WerpGetPathOfWERTempDirectory
0x180018d14  mov     ebx, eax
0x180018d16  test    eax, eax
0x180018d18  js      loc_180018E00
0x180018d1e  mov     r9, rdi
0x180018d21  lea     r8, [rbp+1F0h+var_240]
0x180018d25  lea     rdx, aWsWs; "%ws\\%ws"
0x180018d2c  lea     rcx, [rsp+2F0h+var_2C8]
0x180018d31  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180018d36  mov     ebx, eax
0x180018d38  test    eax, eax
0x180018d3a  js      loc_180018E00
0x180018d40  lea     rdx, [rsp+2F0h+hObject]
0x180018d45  mov     rcx, [rsp+2F0h+var_2C8]; wchar_t *
0x180018d4a  call    ?UtilVerifyAndLockDirectory@@YAJPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; UtilVerifyAndLockDirectory(wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *)
0x180018d4f  mov     ebx, eax
0x180018d51  test    eax, eax
0x180018d53  js      loc_180018E00
0x180018d59  lea     rdx, [rbp+1F0h+var_250]; struct _GUID *
0x180018d5d  mov     rcx, rdi; wchar_t *
0x180018d60  call    ?UtilParseGuidString@@YAJPEB_WPEAU_GUID@@@Z; UtilParseGuidString(wchar_t const *,_GUID *)
0x180018d65  mov     ebx, eax
0x180018d67  test    eax, eax
0x180018d69  js      loc_180018E00
0x180018d6f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180018d73  inc     r8
0x180018d76  cmp     [rdi+r8*2], r15w
0x180018d7b  jnz     short loc_180018D73
0x180018d7d  mov     rdx, rdi
0x180018d80  lea     rcx, [rbp+1F0h+var_270]
0x180018d84  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180018d89  test    al, al
0x180018d8b  jz      short loc_180018DF4
0x180018d8d  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows\\Windows E"...
0x180018d94  lea     rcx, [rsp+2F0h+var_2A0]; this
0x180018d99  call    ?AddSessionsFromRegistry@CEtwTraceManager@@QEAAJPEB_W@Z; CEtwTraceManager::AddSessionsFromRegistry(wchar_t const *)
0x180018d9e  mov     ebx, eax
0x180018da0  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\Windows E"...
0x180018da7  lea     rcx, [rsp+2F0h+var_2A0]; this
0x180018dac  call    ?AddSessionsFromRegistry@CEtwTraceManager@@QEAAJPEB_W@Z; CEtwTraceManager::AddSessionsFromRegistry(wchar_t const *)
0x180018db1  mov     edi, eax
0x180018db3  lea     rcx, [rsp+2F0h+var_2A0]; this
0x180018db8  call    ?AddWprcInstancesFromRegistry@CEtwTraceManager@@QEAAJPEB_W@Z; CEtwTraceManager::AddWprcInstancesFromRegistry(wchar_t const *)
0x180018dbd  test    ebx, ebx
0x180018dbf  jns     short loc_180018DC9
0x180018dc1  test    edi, edi
0x180018dc3  jns     short loc_180018DC9
0x180018dc5  test    eax, eax
0x180018dc7  js      short loc_180018DDE
0x180018dc9  lea     r8, [r14+28h]; struct utl::recursive_mutex *
0x180018dcd  mov     rdx, [rsp+2F0h+var_2C8]; wchar_t *
0x180018dd2  lea     rcx, [rsp+2F0h+var_2A0]; this
0x180018dd7  call    ?FlushAllSessions@CEtwTraceManager@@QEAAJPEB_WAEAVrecursive_mutex@utl@@@Z; CEtwTraceManager::FlushAllSessions(wchar_t const *,utl::recursive_mutex &)
0x180018ddc  mov     ebx, eax
0x180018dde  lea     r8, [rsi+238h]; unsigned int *
0x180018de5  mov     [r8], r15d
0x180018de8  mov     rdx, [rsp+2F0h+var_2C8]; wchar_t *
0x180018ded  call    ?SnapHostOrGuestOneTrace@CWerService@@AEAAJPEB_WPEAK@Z; CWerService::SnapHostOrGuestOneTrace(wchar_t const *,ulong *)
0x180018df2  jmp     short loc_180018E00
0x180018df4  mov     ebx, 8007000Eh
0x180018df9  jmp     short loc_180018E00
0x180018dfb  mov     ebx, 80070057h
0x180018e00  mov     rcx, [rsp+2F0h+hObject]; hObject
0x180018e05  lea     rax, [rcx+1]
0x180018e09  cmp     rax, 1
0x180018e0d  jbe     short loc_180018E15
0x180018e0f  call    cs:__imp_CloseHandle
0x180018e15  mov     [rsi+2Ch], ebx
0x180018e18  mov     eax, ebx
0x180018e1a  sar     eax, 1Fh
0x180018e1d  and     eax, 1
0x180018e20  sub     eax, 0FFF0000h
0x180018e25  mov     [rsi+28h], eax
0x180018e28  mov     rax, qword ptr [rsp+2F0h+var_2A0+8]
0x180018e2d  sub     rax, qword ptr [rsp+2F0h+var_2A0]
0x180018e32  sar     rax, 3
0x180018e36  add     [rsi+238h], eax
0x180018e3c  lea     rcx, [rsp+2F0h+var_2A0]; this
0x180018e41  call    ??1CEtwTraceManager@@QEAA@XZ; CEtwTraceManager::~CEtwTraceManager(void)
0x180018e46  nop
0x180018e47  lea     rax, [rsp+2F0h+var_2B8]
0x180018e4c  mov     rcx, [rsp+2F0h+var_2C8]; void *
0x180018e51  cmp     rcx, rax
0x180018e54  jz      short loc_180018E62
0x180018e56  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018e5d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180018e62  mov     eax, ebx
0x180018e64  mov     rcx, [rbp+1F0h+var_30]
0x180018e6b  xor     rcx, rsp; StackCookie
0x180018e6e  call    __security_check_cookie
0x180018e73  mov     rbx, [rsp+2F0h+arg_18]
0x180018e7b  add     rsp, 2D0h
0x180018e82  pop     r15
0x180018e84  pop     r14
0x180018e86  pop     rdi
0x180018e87  pop     rsi
0x180018e88  pop     rbp
0x180018e89  retn
```

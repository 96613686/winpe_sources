# WebPlatStoragePathManager::WebPlatStoragePathManager(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180040900`
- end: `0x180040c63`
- name: `??0WebPlatStoragePathManager@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `867`
- prototype: `char *__fastcall(char *, const wchar_t *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180041a88`

## callees

- `0x180008270`
- `0x18001c800`
- `0x18003fc20`
- `0x180040900`
- `0x180040c6c`
- `0x180040d58`
- `0x1800412c4`
- `0x18004fd6c`
- `0x180061c90`
- `0x180063d58`
- `0x180064ec8`
- `0x180066010`
- `0x18006c780`
- `0x18006ed14`
- `0x180080fb0`
- `0x18008414c`
- `0x1800a54a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040b55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040b55`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800409ca`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800409ca`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180040a27`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x180040a27`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180040b3f`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x180040b3f`

## string_xrefs

- `0x1800409d4`: `onecoreuap\inetcore\webplatstorageserver\clientmanager\webplatstoragepathmanager.cxx`
- `0x180040a46`: `onecoreuap\inetcore\webplatstorageserver\clientmanager\webplatstoragepathmanager.cxx`
- `0x180040bd8`: `onecoreuap\inetcore\webplatstorageserver\clientmanager\webplatstoragepathmanager.cxx`
- `0x180040b98`: `CacheStorage\`
- `0x180040b8f`: `CacheStorage\EDP\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char *__fastcall WebPlatStoragePathManager::WebPlatStoragePathManager(char *a1, const wchar_t *a2)
{
  const wchar_t *v4; // rcx
  const char *v5; // r9
  const wchar_t *v6; // rdx
  void *v7; // rbx
  const char *v8; // r9
  __int64 PackageRootFolder; // rsi
  char v10; // di
  unsigned __int64 i; // rbx
  wchar_t *v12; // r8
  __int128 *p_Src; // rdx
  __int64 v14; // rax
  HANDLE hObject[3]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 Src; // [rsp+50h] [rbp-B0h] BYREF
  __m128i v18; // [rsp+60h] [rbp-A0h]
  __int128 v19; // [rsp+70h] [rbp-90h] BYREF
  __m128i si128; // [rsp+80h] [rbp-80h]
  __int128 v21; // [rsp+90h] [rbp-70h] BYREF
  __m128i v22; // [rsp+A0h] [rbp-60h]
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  hObject[1] = a1;
  `eh vector constructor iterator'(a1, 0x20u, 3u, std::wstring::wstring, std::wstring::~wstring);
  v19 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19) = 0;
  Src = 0;
  v18 = si128;
  LOWORD(Src) = 0;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v4 = a2;
  else
    v4 = *(const wchar_t **)a2;
  if ( *((_QWORD *)a2 + 2) == 12 && !wmemcmp(v4, L"mshtmpad.exe", 0xCu) )
  {
    if ( !GetTempPathW(0x105u, Buffer) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\webplatstoragepathmanager.cxx",
        v5);
    std::wstring::assign(&v19, Buffer);
    std::wstring::assign(&Src, Buffer);
  }
  else
  {
    WebPlatStoragePathManager::GetCallerThreadToken(hObject);
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v6 = a2;
    else
      v6 = *(const wchar_t **)a2;
    v7 = (void *)OpenStateExplicit(hObject[0], v6);
    hObject[2] = v7;
    if ( !v7 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x21,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\clientmanager\\webplatstoragepathmanager.cxx",
        v8);
    PackageRootFolder = WebPlatStoragePathManager::GetPackageRootFolder(&v21, v7);
    if ( &v19 != (__int128 *)PackageRootFolder )
    {
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(v19, 2 * si128.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v19) = 0;
      v19 = *(_OWORD *)PackageRootFolder;
      si128 = *(__m128i *)(PackageRootFolder + 16);
      *(_QWORD *)(PackageRootFolder + 16) = 0;
      *(_QWORD *)(PackageRootFolder + 24) = 7;
      *(_WORD *)PackageRootFolder = 0;
    }
    if ( v22.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(v21, 2 * v22.m128i_i64[1] + 2);
    v10 = IsEdgePackage(a2);
    WebPlatStoragePathManager::GetAppDataFolderHelper(&v21, v7);
    if ( v10 )
      WebPlatStoragePathManager::AppendUserProfileFolder(&v21);
    if ( v18.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>(Src, 2 * v18.m128i_i64[1] + 2);
    Src = v21;
    v18 = v22;
    CloseState(v7);
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
  }
  for ( i = 0; i < 3; ++i )
  {
    if ( (_DWORD)i )
    {
      if ( (_DWORD)i != 1 )
      {
        v12 = L"AC\\Microsoft\\";
        p_Src = &v19;
        goto LABEL_34;
      }
      v12 = L"CacheStorage\\EDP\\";
    }
    else
    {
      v12 = L"CacheStorage\\";
    }
    p_Src = &Src;
LABEL_34:
    v14 = std::operator+<unsigned short>(&v21, p_Src, v12);
    std::wstring::operator=(&a1[32 * i], v14);
    std::wstring::~wstring(&v21);
  }
  if ( v18.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(Src, 2 * v18.m128i_i64[1] + 2);
  v18 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v19, 2 * si128.m128i_i64[1] + 2);
  return a1;
}

```

## disassembly

```asm
0x180040900  mov     [rsp-8+arg_10], rbx
0x180040905  mov     [rsp-8+arg_18], rsi
0x18004090a  push    rbp
0x18004090b  push    rdi
0x18004090c  push    r14
0x18004090e  lea     rbp, [rsp-1D0h]
0x180040916  sub     rsp, 2D0h
0x18004091d  mov     rax, cs:__security_cookie
0x180040924  xor     rax, rsp
0x180040927  mov     [rbp+1E0h+var_20], rax
0x18004092e  mov     rdi, rdx
0x180040931  mov     r14, rcx
0x180040934  mov     [rsp+2E0h+var_2A0], rcx
0x180040939  mov     [rsp+2E0h+var_2B0], 0
0x180040941  lea     rax, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040948  mov     [rsp+2E0h+var_2C0], rax; int
0x18004094d  lea     r9, ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x180040954  mov     edx, 20h ; ' '; unsigned __int64
0x180040959  lea     r8d, [rdx-1Dh]; unsigned __int64
0x18004095d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180040962  nop
0x180040963  xorps   xmm0, xmm0
0x180040966  movups  [rsp+2E0h+var_270], xmm0
0x18004096b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180040973  movdqu  [rbp+1E0h+var_260], xmm1
0x180040978  xor     eax, eax
0x18004097a  mov     word ptr [rsp+2E0h+var_270], ax
0x18004097f  movups  [rsp+2E0h+Src], xmm0
0x180040984  movdqu  [rsp+2E0h+var_280], xmm1
0x18004098a  mov     word ptr [rsp+2E0h+Src], ax
0x18004098f  cmp     qword ptr [rdi+18h], 7
0x180040994  jbe     short loc_18004099B
0x180040996  mov     rcx, [rdi]
0x180040999  jmp     short loc_18004099E
0x18004099b  mov     rcx, rdi; S1
0x18004099e  mov     r8d, 0Ch; N
0x1800409a4  cmp     [rdi+10h], r8
0x1800409a8  jnz     short loc_180040A08
0x1800409aa  lea     rdx, aMshtmpadExe; "mshtmpad.exe"
0x1800409b1  call    wmemcmp
0x1800409b6  test    eax, eax
0x1800409b8  jnz     short loc_180040A08
0x1800409ba  mov     rbx, [rbp+1E8h]
0x1800409c1  lea     rdx, [rbp+1E0h+Buffer]; lpBuffer
0x1800409c5  mov     ecx, 105h; nBufferLength
0x1800409ca  call    cs:__imp_GetTempPathW
0x1800409d0  test    eax, eax
0x1800409d2  jnz     short loc_1800409E7
0x1800409d4  lea     r8, aOnecoreuapInet_31; "onecoreuap\\inetcore\\webplatstorageser"...
0x1800409db  lea     edx, [rax+18h]; void *
0x1800409de  mov     rcx, rbx; this
0x1800409e1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800409e7  lea     rdx, [rbp+1E0h+Buffer]
0x1800409eb  lea     rcx, [rsp+2E0h+var_270]
0x1800409f0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800409f5  lea     rdx, [rbp+1E0h+Buffer]
0x1800409f9  lea     rcx, [rsp+2E0h+Src]
0x1800409fe  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180040a03  jmp     loc_180040B5B
0x180040a08  lea     rcx, [rsp+2E0h+hObject]; TokenHandle
0x180040a0d  call    ?GetCallerThreadToken@WebPlatStoragePathManager@@CA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; WebPlatStoragePathManager::GetCallerThreadToken(void)
0x180040a12  nop
0x180040a13  cmp     qword ptr [rdi+18h], 7
0x180040a18  jbe     short loc_180040A1F
0x180040a1a  mov     rdx, [rdi]
0x180040a1d  jmp     short loc_180040A22
0x180040a1f  mov     rdx, rdi
0x180040a22  mov     rcx, [rsp+2E0h+hObject]
0x180040a27  call    cs:__imp_OpenStateExplicit
0x180040a2d  mov     rbx, rax
0x180040a30  mov     [rsp+2E0h+var_298], rax
0x180040a35  test    rax, rax
0x180040a38  setnz   al
0x180040a3b  mov     rcx, [rbp+1E8h]; this
0x180040a42  test    al, al
0x180040a44  jnz     short loc_180040A58
0x180040a46  lea     r8, aOnecoreuapInet_31; "onecoreuap\\inetcore\\webplatstorageser"...
0x180040a4d  mov     edx, 21h ; '!'; void *
0x180040a52  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180040a58  mov     rdx, rbx
0x180040a5b  lea     rcx, [rbp+1E0h+var_250]
0x180040a5f  call    ?GetPackageRootFolder@WebPlatStoragePathManager@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; WebPlatStoragePathManager::GetPackageRootFolder(void *)
0x180040a64  mov     rsi, rax
0x180040a67  lea     rax, [rsp+2E0h+var_270]
0x180040a6c  cmp     rax, rsi
0x180040a6f  jz      short loc_180040AC0
0x180040a71  mov     rdx, qword ptr [rbp+1E0h+var_260+8]
0x180040a75  cmp     rdx, 7
0x180040a79  jbe     short loc_180040A8D
0x180040a7b  lea     rdx, ds:2[rdx*2]
0x180040a83  mov     rcx, qword ptr [rsp+2E0h+var_270]
0x180040a88  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180040a8d  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180040a95  movdqu  [rbp+1E0h+var_260], xmm0
0x180040a9a  xor     eax, eax
0x180040a9c  mov     word ptr [rsp+2E0h+var_270], ax
0x180040aa1  movups  xmm0, xmmword ptr [rsi]
0x180040aa4  movups  [rsp+2E0h+var_270], xmm0
0x180040aa9  movups  xmm1, xmmword ptr [rsi+10h]
0x180040aad  movups  [rbp+1E0h+var_260], xmm1
0x180040ab1  mov     [rsi+10h], rax
0x180040ab5  mov     qword ptr [rsi+18h], 7
0x180040abd  mov     [rsi], ax
0x180040ac0  mov     rdx, [rbp+1E0h+var_238]
0x180040ac4  cmp     rdx, 7
0x180040ac8  jbe     short loc_180040ADB
0x180040aca  lea     rdx, ds:2[rdx*2]
0x180040ad2  mov     rcx, qword ptr [rbp+1E0h+var_250]
0x180040ad6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180040adb  mov     rcx, rdi
0x180040ade  call    ?IsEdgePackage@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsEdgePackage(std::wstring const &)
0x180040ae3  mov     dil, al
0x180040ae6  mov     rdx, rbx
0x180040ae9  lea     rcx, [rbp+1E0h+var_250]
0x180040aed  call    ?GetAppDataFolderHelper@WebPlatStoragePathManager@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; WebPlatStoragePathManager::GetAppDataFolderHelper(void *)
0x180040af2  mov     [rsp+2E0h+var_2B0], 1
0x180040afa  test    dil, dil
0x180040afd  jz      short loc_180040B08
0x180040aff  lea     rcx, [rbp+1E0h+var_250]; Src
0x180040b03  call    ?AppendUserProfileFolder@WebPlatStoragePathManager@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WebPlatStoragePathManager::AppendUserProfileFolder(std::wstring &)
0x180040b08  mov     rdx, qword ptr [rsp+2E0h+var_280+8]
0x180040b0d  cmp     rdx, 7
0x180040b11  jbe     short loc_180040B25
0x180040b13  lea     rdx, ds:2[rdx*2]
0x180040b1b  mov     rcx, qword ptr [rsp+2E0h+Src]
0x180040b20  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180040b25  movups  xmm0, [rbp+1E0h+var_250]
0x180040b29  movups  [rsp+2E0h+Src], xmm0
0x180040b2e  movups  xmm1, xmmword ptr [rbp-60h]
0x180040b32  movups  [rsp+2E0h+var_280], xmm1
0x180040b37  test    rbx, rbx
0x180040b3a  jz      short loc_180040B46
0x180040b3c  mov     rcx, rbx
0x180040b3f  call    cs:__imp_CloseState
0x180040b45  nop
0x180040b46  mov     rcx, [rsp+2E0h+hObject]; hObject
0x180040b4b  lea     rax, [rcx-1]
0x180040b4f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180040b53  ja      short loc_180040B5B
0x180040b55  call    cs:__imp_CloseHandle
0x180040b5b  xor     ebx, ebx
0x180040b5d  cmp     rbx, 3
0x180040b61  jnb     loc_180040BEA
0x180040b67  mov     rdi, rbx
0x180040b6a  shl     rdi, 5
0x180040b6e  add     rdi, r14
0x180040b71  mov     edx, ebx
0x180040b73  test    ebx, ebx
0x180040b75  jz      short loc_180040B98
0x180040b77  sub     edx, 1
0x180040b7a  jz      short loc_180040B8F
0x180040b7c  cmp     edx, 1
0x180040b7f  jnz     short loc_180040BC6
0x180040b81  lea     r8, aAcMicrosoft; "AC\\Microsoft\\"
0x180040b88  lea     rdx, [rsp+2E0h+var_270]
0x180040b8d  jmp     short loc_180040BA4
0x180040b8f  lea     r8, aCachestorageEd_0; "CacheStorage\\EDP\\"
0x180040b96  jmp     short loc_180040B9F
0x180040b98  lea     r8, aCachestorage; "CacheStorage\\"
0x180040b9f  lea     rdx, [rsp+2E0h+Src]; Src
0x180040ba4  lea     rcx, [rbp+1E0h+var_250]; void *
0x180040ba8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180040bad  mov     rdx, rax
0x180040bb0  mov     rcx, rdi
0x180040bb3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180040bb8  lea     rcx, [rbp+1E0h+var_250]; void *
0x180040bbc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040bc1  inc     rbx
0x180040bc4  jmp     short loc_180040B5D
0x180040bc6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180040bcb  mov     rcx, [rbp+1E8h]; this
0x180040bd2  mov     r9d, 8000FFFFh; char *
0x180040bd8  lea     r8, aOnecoreuapInet_31; "onecoreuap\\inetcore\\webplatstorageser"...
0x180040bdf  mov     edx, 44h ; 'D'; void *
0x180040be4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040bea  mov     rdx, qword ptr [rsp+2E0h+var_280+8]
0x180040bef  cmp     rdx, 7
0x180040bf3  jbe     short loc_180040C07
0x180040bf5  lea     rdx, ds:2[rdx*2]
0x180040bfd  mov     rcx, qword ptr [rsp+2E0h+Src]
0x180040c02  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180040c07  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180040c0f  movdqu  [rsp+2E0h+var_280], xmm0
0x180040c15  xor     ecx, ecx
0x180040c17  mov     word ptr [rsp+2E0h+Src], cx
0x180040c1c  mov     rdx, qword ptr [rbp+1E0h+var_260+8]
0x180040c20  cmp     rdx, 7
0x180040c24  jbe     short loc_180040C39
0x180040c26  lea     rdx, ds:2[rdx*2]
0x180040c2e  mov     rcx, qword ptr [rsp+2E0h+var_270]
0x180040c33  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180040c38  nop
0x180040c39  mov     rax, r14
0x180040c3c  mov     rcx, [rbp+1E0h+var_20]
0x180040c43  xor     rcx, rsp; StackCookie
0x180040c46  call    __security_check_cookie
0x180040c4b  lea     r11, [rsp+2E0h+var_10]
0x180040c53  mov     rbx, [r11+30h]
0x180040c57  mov     rsi, [r11+38h]
0x180040c5b  mov     rsp, r11
0x180040c5e  pop     r14
0x180040c60  pop     rdi
0x180040c61  pop     rbp
0x180040c62  retn
```

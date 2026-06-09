# windiag::module_resource_ex(char const *,char const *,unsigned __int64 *,HINSTANCE__ *)

- ea: `0x18007875c`
- end: `0x180078c26`
- name: `?module_resource_ex@windiag@@YAPEBDPEBD0PEA_KPEAUHINSTANCE__@@@Z`
- size: `1226`
- prototype: `const char *__fastcall(LPCSTR lpType, LPCSTR lpName, char *, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180075fa0`
- `0x18007701c`
- `0x1800780f4`
- `0x18008eb60`

## callees

- `0x180004510`
- `0x1800048c0`
- `0x18000491c`
- `0x180004aac`
- `0x180004b14`
- `0x1800054e4`
- `0x180005520`
- `0x18003a4cc`
- `0x18003a52c`
- `0x18003af08`
- `0x18003b0bc`
- `0x180048c8c`
- `0x180049674`
- `0x1800511ac`
- `0x18006dc58`
- `0x180075258`
- `0x180075350`
- `0x180075410`
- `0x18007556c`
- `0x18007875c`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180078ace`
- `msvcp_win!_Mtx_unlock` at `0x180078b5e`
- `msvcp_win!_Mtx_unlock` at `0x180078ace`
- `msvcp_win!_Mtx_unlock` at `0x180078b5e`
- `msvcp_win!_Mtx_lock` at `0x180078829`
- `msvcp_win!_Mtx_lock` at `0x180078829`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180078838`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180078859`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180078838`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180078859`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18007892a`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18007892a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180078939`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180078939`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180078954`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180078954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800789b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800789b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078b0d`
- `Cabinet!__imp_CreateDecompressor` at `0x180078978`
- `Cabinet!__imp_CreateDecompressor` at `0x180078978`
- `Cabinet!__imp_Decompress` at `0x1800789a8`
- `Cabinet!__imp_Decompress` at `0x180078a3c`
- `Cabinet!__imp_Decompress` at `0x1800789a8`
- `Cabinet!__imp_Decompress` at `0x180078a3c`
- `Cabinet!__imp_CloseDecompressor` at `0x180078ac0`
- `Cabinet!__imp_CloseDecompressor` at `0x180078b4c`
- `Cabinet!__imp_CloseDecompressor` at `0x180078ac0`
- `Cabinet!__imp_CloseDecompressor` at `0x180078b4c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FindResourceA` at `0x180078912`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FindResourceA` at `0x180078912`

## pseudocode

```c
const char *__fastcall windiag::module_resource_ex(LPCSTR lpType, LPCSTR lpName, char *a3, unsigned __int64 *a4)
{
  __int64 v8; // rbx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rbx
  _QWORD *v12; // rax
  __int64 v13; // rcx
  LPVOID v14; // rdi
  HRSRC ResourceA; // rax
  HRSRC v16; // rbx
  __int64 v17; // r14
  HGLOBAL Resource; // rax
  size_t v19; // r14
  char *v20; // rbx
  DWORD LastError; // eax
  __int64 v22; // rcx
  __int64 v24; // rcx
  _QWORD *v25; // rax
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  void *v27[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+48h] [rbp-B8h]
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v30[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 *v31; // [rsp+70h] [rbp-90h] BYREF
  __int128 v32; // [rsp+78h] [rbp-88h] BYREF
  __int64 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int128 v35; // [rsp+98h] [rbp-68h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  _BYTE pExceptionObject[1072]; // [rsp+C0h] [rbp-40h] BYREF

  v8 = -1;
  if ( __TSS0__1__module_resource_ex_windiag__YAPEBDPEBD0PEA_KPEAUHINSTANCE_____Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                                                                                  + 4LL) )
  {
    Init_thread_header(&__TSS0__1__module_resource_ex_windiag__YAPEBDPEBD0PEA_KPEAUHINSTANCE_____Z_4HA);
    if ( __TSS0__1__module_resource_ex_windiag__YAPEBDPEBD0PEA_KPEAUHINSTANCE_____Z_4HA == -1 )
    {
      `windiag::module_resource_ex'::`2'::res_map = 0;
      qword_1800BEB98 = 0;
      v25 = operator new(0x88u);
      *v25 = v25;
      v25[1] = v25;
      v25[2] = v25;
      *((_WORD *)v25 + 12) = 257;
      `windiag::module_resource_ex'::`2'::res_map = (__int64)v25;
      atexit(`windiag::module_resource_ex'::`2'::`dynamic atexit destructor for 'res_map'');
      Init_thread_footer(&__TSS0__1__module_resource_ex_windiag__YAPEBDPEBD0PEA_KPEAUHINSTANCE_____Z_4HA);
    }
  }
  v31 = a4;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v9 = -1;
  do
    ++v9;
  while ( lpName[v9] );
  std::string::_Construct<1,char const *>(&v32);
  v35 = 0;
  v36 = 0;
  v37 = 0;
  do
    ++v8;
  while ( lpType[v8] );
  std::string::_Construct<1,char const *>(&v35);
  v30[2] = `windiag::module_resource_ex'::`2'::res_mtx;
  if ( _Mtx_lock((_Mtx_t)`windiag::module_resource_ex'::`2'::res_mtx) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( dword_1800BE38C == 0x7FFFFFFF )
  {
    dword_1800BE38C = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  std::_Tree<std::_Tmap_traits<std::tuple<std::string,std::string,HINSTANCE__ *>,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>,std::less<std::tuple<std::string,std::string,HINSTANCE__ *>>,std::allocator<std::pair<std::tuple<std::string,std::string,HINSTANCE__ *> const,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>>>,0>>::_Find_lower_bound<std::tuple<std::string,std::string,HINSTANCE__ *>>(
    v10,
    v27,
    &v31);
  v11 = v28;
  if ( *(_BYTE *)(v28 + 25)
    || (unsigned __int8)std::operator<<char>(&v35, v28 + 72)
    || !(unsigned __int8)std::operator<<char>(v11 + 72, &v35)
    && ((unsigned __int8)std::operator<<char>(&v32, v11 + 40)
     || !(unsigned __int8)std::operator<<char>(v11 + 40, &v32) && (unsigned __int64)v31 < *(_QWORD *)(v11 + 32))
    || v11 == `windiag::module_resource_ex'::`2'::res_map )
  {
    *(_QWORD *)a3 = 0;
    ResourceA = FindResourceA((HMODULE)a4, lpName, lpType);
    v16 = ResourceA;
    if ( ResourceA )
    {
      v17 = SizeofResource((HMODULE)a4, ResourceA);
      Resource = LoadResource((HMODULE)a4, v16);
      if ( Resource )
      {
        if ( (_DWORD)v17 )
        {
          v14 = LockResource(Resource);
          if ( v14 )
          {
            *(_QWORD *)a3 = v17;
            v26 = 0;
            if ( (unsigned int)CreateDecompressor(2, 0, &v26) )
            {
              Size = 0;
              if ( !(unsigned int)Decompress(v26, v14, *(_QWORD *)a3, 0, 0, &Size) )
              {
                if ( GetLastError() == 122 )
                {
                  v19 = Size;
                  *(_OWORD *)v27 = 0;
                  v28 = 0;
                  if ( Size )
                  {
                    std::vector<char>::_Buy_nonzero(v27, Size);
                    v20 = (char *)v27[0];
                    memset_0(v27[0], 0, v19);
                    v27[1] = &v20[v19];
                    v30[0] = 0;
                    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(v30);
                  }
                  if ( !(unsigned int)Decompress(
                                        v26,
                                        v14,
                                        *(_QWORD *)a3,
                                        v27[0],
                                        (char *)v27[1] - (char *)v27[0],
                                        &Size) )
                  {
                    LastError = GetLastError();
                    if ( LastError )
                    {
                      windiag::system_exception::system_exception(
                        (windiag::system_exception *)pExceptionObject,
                        LastError,
                        0,
                        "[%s:%d] failed; ",
                        "module_resource_ex",
                        527);
                      throw (windiag::system_exception *)pExceptionObject;
                    }
                  }
                  if ( Size <= (char *)v27[1] - (char *)v27[0] )
                  {
                    std::vector<unsigned char>::resize(v27);
                    v14 = v27[0];
                    *(_QWORD *)a3 = (char *)v27[1] - (char *)v27[0];
                    std::_Tree<std::_Tmap_traits<std::tuple<std::string,std::string,HINSTANCE__ *>,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>,std::less<std::tuple<std::string,std::string,HINSTANCE__ *>>,std::allocator<std::pair<std::tuple<std::string,std::string,HINSTANCE__ *> const,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>>>,0>>::emplace<std::tuple<std::string,std::string,HINSTANCE__ *>,std::vector<char>>(
                      v22,
                      v30,
                      &v31,
                      v27);
                    std::vector<char>::~vector<char>(v27);
LABEL_40:
                    if ( v26 )
                    {
                      v26 = 0;
                      CloseDecompressor();
                    }
                    v26 = 0;
                    goto LABEL_43;
                  }
                  std::vector<char>::~vector<char>(v27);
                }
                else if ( GetLastError() == 605 )
                {
                  v30[0] = v14;
                  v30[1] = *(_QWORD *)a3;
                  std::_Tree<std::_Tmap_traits<std::tuple<std::string,std::string,HINSTANCE__ *>,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>,std::less<std::tuple<std::string,std::string,HINSTANCE__ *>>,std::allocator<std::pair<std::tuple<std::string,std::string,HINSTANCE__ *> const,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>>>,0>>::emplace<std::tuple<std::string,std::string,HINSTANCE__ *>,std::pair<char const *,unsigned __int64>>(
                    v24,
                    v27,
                    &v31,
                    v30);
                  goto LABEL_40;
                }
              }
            }
            if ( v26 )
            {
              v26 = 0;
              CloseDecompressor();
            }
          }
        }
      }
    }
    _Mtx_unlock((_Mtx_t)`windiag::module_resource_ex'::`2'::res_mtx);
    std::string::~string(&v35);
    std::string::~string(&v32);
    return 0;
  }
  v12 = (_QWORD *)(v11 + 104);
  if ( *(char *)(v11 + 128) == -1 )
    std::_Variant_dispatcher<std::integer_sequence<unsigned __int64,0>>::_Dispatch2<char const *,_lambda_614acedd3816982923c7fef7d309115d_,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>> &,1>();
  v13 = *(_QWORD *)(v11 + 112);
  if ( *(_BYTE *)(v11 + 128) )
    v13 -= *v12;
  *(_QWORD *)a3 = v13;
  v14 = (LPVOID)*v12;
LABEL_43:
  _Mtx_unlock((_Mtx_t)`windiag::module_resource_ex'::`2'::res_mtx);
  std::string::~string(&v35);
  std::string::~string(&v32);
  return (const char *)v14;
}

```

## disassembly

```asm
0x18007875c  push    rbp
0x18007875e  push    rbx
0x18007875f  push    rsi
0x180078760  push    rdi
0x180078761  push    r12
0x180078763  push    r13
0x180078765  push    r14
0x180078767  push    r15
0x180078769  lea     rbp, [rsp-408h]
0x180078771  sub     rsp, 508h
0x180078778  mov     rax, cs:__security_cookie
0x18007877f  xor     rax, rsp
0x180078782  mov     [rbp+440h+var_50], rax
0x180078789  mov     r15, r9
0x18007878c  mov     rsi, r8
0x18007878f  mov     r12, rdx
0x180078792  mov     r14, rcx
0x180078795  mov     ecx, cs:_tls_index
0x18007879b  mov     rax, gs:58h
0x1800787a4  mov     edx, 4
0x1800787a9  mov     rax, [rax+rcx*8]
0x1800787ad  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800787b1  xor     r13d, r13d
0x1800787b4  mov     eax, [rdx+rax]
0x1800787b7  cmp     cs:?$TSS0@?1??module_resource_ex@windiag@@YAPEBDPEBD0PEA_KPEAUHINSTANCE__@@@Z@4HA, eax
0x1800787bd  jg      loc_180078BBA
0x1800787c3  mov     [rsp+540h+var_4D0], r15
0x1800787c8  xorps   xmm0, xmm0
0x1800787cb  movups  [rsp+540h+var_4C8], xmm0
0x1800787d0  mov     [rbp+440h+var_4B8], r13
0x1800787d4  mov     [rbp+440h+var_4B0], r13
0x1800787d8  mov     r8, rbx
0x1800787db  inc     r8
0x1800787de  cmp     [r12+r8], r13b
0x1800787e2  jnz     short loc_1800787DB
0x1800787e4  mov     rdx, r12
0x1800787e7  lea     rcx, [rsp+540h+var_4C8]
0x1800787ec  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800787f1  nop
0x1800787f2  xorps   xmm0, xmm0
0x1800787f5  movups  [rbp+440h+var_4A8], xmm0
0x1800787f9  mov     [rbp+440h+var_498], r13
0x1800787fd  mov     [rbp+440h+var_490], r13
0x180078801  inc     rbx
0x180078804  cmp     [r14+rbx], r13b
0x180078808  jnz     short loc_180078801
0x18007880a  mov     r8, rbx
0x18007880d  mov     rdx, r14
0x180078810  lea     rcx, [rbp+440h+var_4A8]
0x180078814  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180078819  nop
0x18007881a  lea     rax, ?res_mtx@?1??module_resource_ex@windiag@@YAPEBDPEBD0PEA_KPEAUHINSTANCE__@@@Z@4Vmutex@std@@A; std::mutex `windiag::module_resource_ex(char const *,char const *,unsigned __int64 *,HINSTANCE__ *)'::`2'::res_mtx
0x180078821  mov     [rsp+540h+var_4D8], rax
0x180078826  mov     rcx, rax; _Mtx_t
0x180078829  call    cs:__imp__Mtx_lock
0x18007882f  test    eax, eax
0x180078831  jz      short loc_18007883F
0x180078833  mov     ecx, 5
0x180078838  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18007883e  int     3; Trap to Debugger
0x18007883f  mov     eax, cs:dword_1800BE38C
0x180078845  cmp     eax, 7FFFFFFFh
0x18007884a  jnz     short loc_180078860
0x18007884c  dec     eax
0x18007884e  mov     cs:dword_1800BE38C, eax
0x180078854  mov     ecx, 6
0x180078859  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18007885f  nop
0x180078860  lea     r8, [rsp+540h+var_4D0]
0x180078865  lea     rdx, [rsp+540h+var_508]
0x18007886a  call    ??$_Find_lower_bound@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@U?$less@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@@std@@PEAX@std@@@1@AEBV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@1@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::string,std::string,HINSTANCE__ *>,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>,std::less<std::tuple<std::string,std::string,HINSTANCE__ *>>,std::allocator<std::pair<std::tuple<std::string,std::string,HINSTANCE__ *> const,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>>>,0>>::_Find_lower_bound<std::tuple<std::string,std::string,HINSTANCE__ *>>(std::tuple<std::string,std::string,HINSTANCE__ *> const &)
0x18007886f  mov     rbx, [rsp+540h+var_4F8]
0x180078874  cmp     [rbx+19h], r13b
0x180078878  jnz     loc_180078906
0x18007887e  lea     rdx, [rbx+48h]
0x180078882  lea     rcx, [rbp+440h+var_4A8]
0x180078886  call    ??$?MDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@0@Z; std::operator<<char>(std::string const &,std::string const &)
0x18007888b  test    al, al
0x18007888d  jnz     short loc_180078906
0x18007888f  lea     rdx, [rbp+440h+var_4A8]
0x180078893  lea     rcx, [rbx+48h]
0x180078897  call    ??$?MDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@0@Z; std::operator<<char>(std::string const &,std::string const &)
0x18007889c  test    al, al
0x18007889e  jnz     short loc_1800788CF
0x1800788a0  lea     rdx, [rbx+28h]
0x1800788a4  lea     rcx, [rsp+540h+var_4C8]
0x1800788a9  call    ??$?MDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@0@Z; std::operator<<char>(std::string const &,std::string const &)
0x1800788ae  test    al, al
0x1800788b0  jnz     short loc_180078906
0x1800788b2  lea     rdx, [rsp+540h+var_4C8]
0x1800788b7  lea     rcx, [rbx+28h]
0x1800788bb  call    ??$?MDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@0@Z; std::operator<<char>(std::string const &,std::string const &)
0x1800788c0  test    al, al
0x1800788c2  jnz     short loc_1800788CF
0x1800788c4  mov     rax, [rbx+20h]
0x1800788c8  cmp     [rsp+540h+var_4D0], rax
0x1800788cd  jb      short loc_180078906
0x1800788cf  cmp     rbx, cs:?res_map@?1??module_resource_ex@windiag@@YAPEBDPEBD0PEA_KPEAUHINSTANCE__@@@Z@4V?$map@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@U?$less@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@@std@@@2@@std@@A; std::map<std::tuple<std::string,std::string,HINSTANCE__ *>,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>> `windiag::module_resource_ex(char const *,char const *,unsigned __int64 *,HINSTANCE__ *)'::`2'::res_map
0x1800788d6  jz      short loc_180078906
0x1800788d8  lea     rax, [rbx+68h]
0x1800788dc  movsx   rcx, byte ptr [rax+18h]
0x1800788e1  add     rcx, 1
0x1800788e5  jz      loc_180078C20
0x1800788eb  mov     rdi, rax
0x1800788ee  cmp     rcx, 1
0x1800788f2  mov     rcx, [rax+8]
0x1800788f6  jz      short loc_1800788FB
0x1800788f8  sub     rcx, [rax]
0x1800788fb  mov     [rsi], rcx
0x1800788fe  mov     rdi, [rdi]
0x180078901  jmp     loc_180078B57
0x180078906  mov     [rsi], r13
0x180078909  mov     r8, r14; lpType
0x18007890c  mov     rdx, r12; lpName
0x18007890f  mov     rcx, r15; hModule
0x180078912  call    cs:__imp_FindResourceA
0x180078918  mov     rbx, rax
0x18007891b  test    rax, rax
0x18007891e  jz      loc_180078AC7
0x180078924  mov     rdx, rax; hResInfo
0x180078927  mov     rcx, r15; hModule
0x18007892a  call    cs:__imp_SizeofResource
0x180078930  mov     r14d, eax
0x180078933  mov     rdx, rbx; hResInfo
0x180078936  mov     rcx, r15; hModule
0x180078939  call    cs:__imp_LoadResource
0x18007893f  test    rax, rax
0x180078942  jz      loc_180078AC7
0x180078948  test    r14d, r14d
0x18007894b  jz      loc_180078AC7
0x180078951  mov     rcx, rax; hResData
0x180078954  call    cs:__imp_LockResource
0x18007895a  mov     rdi, rax
0x18007895d  test    rax, rax
0x180078960  jz      loc_180078AC7
0x180078966  mov     [rsi], r14
0x180078969  mov     [rsp+540h+var_510], r13
0x18007896e  lea     r8, [rsp+540h+var_510]
0x180078973  xor     edx, edx
0x180078975  lea     ecx, [rdx+2]
0x180078978  call    cs:__imp_CreateDecompressor
0x18007897e  test    eax, eax
0x180078980  jz      loc_180078AB1
0x180078986  mov     [rsp+540h+Size], r13
0x18007898b  lea     rax, [rsp+540h+Size]
0x180078990  mov     [rsp+540h+var_518], rax
0x180078995  mov     [rsp+540h+var_520], r13
0x18007899a  xor     r9d, r9d
0x18007899d  mov     r8, [rsi]
0x1800789a0  mov     rdx, rdi
0x1800789a3  mov     rcx, [rsp+540h+var_510]
0x1800789a8  call    cs:__imp_Decompress
0x1800789ae  test    eax, eax
0x1800789b0  jnz     loc_180078AB1
0x1800789b6  call    cs:__imp_GetLastError
0x1800789bc  cmp     eax, 7Ah ; 'z'
0x1800789bf  jnz     loc_180078B0D
0x1800789c5  mov     r14, [rsp+540h+Size]
0x1800789ca  xorps   xmm0, xmm0
0x1800789cd  movdqu  xmmword ptr [rsp+540h+var_508], xmm0
0x1800789d3  mov     [rsp+540h+var_4F8], r13
0x1800789d8  test    r14, r14
0x1800789db  jz      short loc_180078A15
0x1800789dd  mov     rdx, r14
0x1800789e0  lea     rcx, [rsp+540h+var_508]
0x1800789e5  call    ?_Buy_nonzero@?$vector@DV?$allocator@D@std@@@std@@AEAAX_K@Z; std::vector<char>::_Buy_nonzero(unsigned __int64)
0x1800789ea  mov     rbx, [rsp+540h+var_508]
0x1800789ef  mov     r8, r14; Size
0x1800789f2  xor     edx, edx; Val
0x1800789f4  mov     rcx, rbx; void *
0x1800789f7  call    memset_0
0x1800789fc  lea     rax, [rbx+r14]
0x180078a00  mov     [rsp+540h+var_508+8], rax
0x180078a05  mov     [rsp+540h+var_4E8], r13
0x180078a0a  lea     rcx, [rsp+540h+var_4E8]
0x180078a0f  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x180078a14  nop
0x180078a15  mov     r9, [rsp+540h+var_508]
0x180078a1a  mov     rax, [rsp+540h+var_508+8]
0x180078a1f  sub     rax, r9
0x180078a22  lea     rcx, [rsp+540h+Size]
0x180078a27  mov     [rsp+540h+var_518], rcx
0x180078a2c  mov     [rsp+540h+var_520], rax
0x180078a31  mov     r8, [rsi]
0x180078a34  mov     rdx, rdi
0x180078a37  mov     rcx, [rsp+540h+var_510]
0x180078a3c  call    cs:__imp_Decompress
0x180078a42  test    eax, eax
0x180078a44  jnz     short loc_180078A54
0x180078a46  call    cs:__imp_GetLastError
0x180078a4c  test    eax, eax
0x180078a4e  jnz     loc_180078B80
0x180078a54  mov     rax, [rsp+540h+var_508+8]
0x180078a59  sub     rax, [rsp+540h+var_508]
0x180078a5e  mov     rdx, [rsp+540h+Size]
0x180078a63  cmp     rdx, rax
0x180078a66  ja      short loc_180078AA6
0x180078a68  lea     rcx, [rsp+540h+var_508]
0x180078a6d  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180078a72  mov     rdi, [rsp+540h+var_508]
0x180078a77  mov     rax, [rsp+540h+var_508+8]
0x180078a7c  sub     rax, rdi
0x180078a7f  mov     [rsi], rax
0x180078a82  lea     r9, [rsp+540h+var_508]
0x180078a87  lea     r8, [rsp+540h+var_4D0]
0x180078a8c  lea     rdx, [rsp+540h+var_4E8]
0x180078a91  call    ??$emplace@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$vector@DV?$allocator@D@std@@@2@@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@U?$less@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@1@$$QEAV?$vector@DV?$allocator@D@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::string,std::string,HINSTANCE__ *>,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>,std::less<std::tuple<std::string,std::string,HINSTANCE__ *>>,std::allocator<std::pair<std::tuple<std::string,std::string,HINSTANCE__ *> const,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>>>,0>>::emplace<std::tuple<std::string,std::string,HINSTANCE__ *>,std::vector<char>>(std::tuple<std::string,std::string,HINSTANCE__ *> &&,std::vector<char> &&)
0x180078a96  nop
0x180078a97  lea     rcx, [rsp+540h+var_508]
0x180078a9c  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180078aa1  jmp     loc_180078B3D
0x180078aa6  lea     rcx, [rsp+540h+var_508]
0x180078aab  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180078ab0  nop
0x180078ab1  mov     rcx, [rsp+540h+var_510]
0x180078ab6  test    rcx, rcx
0x180078ab9  jz      short loc_180078AC7
0x180078abb  mov     [rsp+540h+var_510], r13
0x180078ac0  call    cs:__imp_CloseDecompressor
0x180078ac6  nop
0x180078ac7  lea     rcx, ?res_mtx@?1??module_resource_ex@windiag@@YAPEBDPEBD0PEA_KPEAUHINSTANCE__@@@Z@4Vmutex@std@@A; _Mtx_t
0x180078ace  call    cs:__imp__Mtx_unlock
0x180078ad4  nop
0x180078ad5  lea     rcx, [rbp+440h+var_4A8]
0x180078ad9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180078ade  lea     rcx, [rsp+540h+var_4C8]
0x180078ae3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180078ae8  xor     eax, eax
0x180078aea  mov     rcx, [rbp+440h+var_50]
0x180078af1  xor     rcx, rsp; StackCookie
0x180078af4  call    __security_check_cookie
0x180078af9  add     rsp, 508h
0x180078b00  pop     r15
0x180078b02  pop     r14
0x180078b04  pop     r13
0x180078b06  pop     r12
0x180078b08  pop     rdi
0x180078b09  pop     rsi
0x180078b0a  pop     rbx
0x180078b0b  pop     rbp
0x180078b0c  retn
0x180078b0d  call    cs:__imp_GetLastError
0x180078b13  nop
0x180078b14  cmp     eax, 25Dh
0x180078b19  jnz     short loc_180078AB1
0x180078b1b  mov     [rsp+540h+var_4E8], rdi
0x180078b20  mov     rax, [rsi]
0x180078b23  mov     [rsp+540h+var_4E0], rax
0x180078b28  lea     r9, [rsp+540h+var_4E8]
0x180078b2d  lea     r8, [rsp+540h+var_4D0]
0x180078b32  lea     rdx, [rsp+540h+var_508]
0x180078b37  call    ??$emplace@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@U?$pair@PEBD_K@2@@?$_Tree@V?$_Tmap_traits@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@U?$less@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@1@$$QEAU?$pair@PEBD_K@1@@Z; std::_Tree<std::_Tmap_traits<std::tuple<std::string,std::string,HINSTANCE__ *>,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>,std::less<std::tuple<std::string,std::string,HINSTANCE__ *>>,std::allocator<std::pair<std::tuple<std::string,std::string,HINSTANCE__ *> const,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>>>,0>>::emplace<std::tuple<std::string,std::string,HINSTANCE__ *>,std::pair<char const *,unsigned __int64>>(std::tuple<std::string,std::string,HINSTANCE__ *> &&,std::pair<char const *,unsigned __int64> &&)
0x180078b3c  nop
0x180078b3d  mov     rcx, [rsp+540h+var_510]
0x180078b42  test    rcx, rcx
0x180078b45  jz      short loc_180078B52
0x180078b47  mov     [rsp+540h+var_510], r13
0x180078b4c  call    cs:__imp_CloseDecompressor
0x180078b52  mov     [rsp+540h+var_510], r13
0x180078b57  lea     rcx, ?res_mtx@?1??module_resource_ex@windiag@@YAPEBDPEBD0PEA_KPEAUHINSTANCE__@@@Z@4Vmutex@std@@A; _Mtx_t
0x180078b5e  call    cs:__imp__Mtx_unlock
0x180078b64  nop
0x180078b65  lea     rcx, [rbp+440h+var_4A8]
0x180078b69  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180078b6e  lea     rcx, [rsp+540h+var_4C8]
0x180078b73  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180078b78  mov     rax, rdi
0x180078b7b  jmp     loc_180078AEA
0x180078b80  mov     edx, eax; __int64
0x180078b82  mov     dword ptr [rsp+540h+var_518], 20Fh
0x180078b8a  lea     rax, aModuleResource; "module_resource_ex"
0x180078b91  mov     [rsp+540h+var_520], rax
0x180078b96  lea     r9, aSDFailed; "[%s:%d] failed; "
0x180078b9d  xor     r8d, r8d; void *
0x180078ba0  lea     rcx, [rbp+440h+pExceptionObject]; this
0x180078ba4  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x180078ba9  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x180078bb0  lea     rcx, [rbp+440h+pExceptionObject]; pExceptionObject
0x180078bb4  call    _CxxThrowException_0
0x180078bba  lea     rcx, ?$TSS0@?1??module_resource_ex@windiag@@YAPEBDPEBD0PEA_KPEAUHINSTANCE__@@@Z@4HA
0x180078bc1  call    _Init_thread_header
0x180078bc6  cmp     cs:?$TSS0@?1??module_resource_ex@windiag@@YAPEBDPEBD0PEA_KPEAUHINSTANCE__@@@Z@4HA, ebx
0x180078bcc  jnz     loc_1800787C3
0x180078bd2  mov     cs:?res_map@?1??module_resource_ex@windiag@@YAPEBDPEBD0PEA_KPEAUHINSTANCE__@@@Z@4V?$map@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@U?$less@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@@std@@@2@@std@@A, r13; std::map<std::tuple<std::string,std::string,HINSTANCE__ *>,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>> `windiag::module_resource_ex(char const *,char const *,unsigned __int64 *,HINSTANCE__ *)'::`2'::res_map
0x180078bd9  mov     cs:qword_1800BEB98, r13
0x180078be0  mov     ecx, 88h; Size
0x180078be5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180078bea  mov     [rax], rax
0x180078bed  mov     [rax+8], rax
0x180078bf1  mov     [rax+10h], rax
0x180078bf5  mov     word ptr [rax+18h], 101h
0x180078bfb  mov     cs:?res_map@?1??module_resource_ex@windiag@@YAPEBDPEBD0PEA_KPEAUHINSTANCE__@@@Z@4V?$map@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@U?$less@V?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@@2@V?$allocator@U?$pair@$$CBV?$tuple@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@PEAUHINSTANCE__@@@std@@V?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@2@@std@@@2@@std@@A, rax; std::map<std::tuple<std::string,std::string,HINSTANCE__ *>,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>>> `windiag::module_resource_ex(char const *,char const *,unsigned __int64 *,HINSTANCE__ *)'::`2'::res_map
0x180078c02  lea     rcx, ??__Fres_map@?1??module_resource_ex@windiag@@YAPEBDPEBD0PEA_KPEAUHINSTANCE__@@@Z@YAXXZ; void (__cdecl *)()
0x180078c09  call    atexit
0x180078c0e  nop
0x180078c0f  lea     rcx, ?$TSS0@?1??module_resource_ex@windiag@@YAPEBDPEBD0PEA_KPEAUHINSTANCE__@@@Z@4HA
0x180078c16  call    _Init_thread_footer
0x180078c1b  jmp     loc_1800787C3
0x180078c20  call    ??$_Dispatch2@PEBDV_lambda_614acedd3816982923c7fef7d309115d_@@AEAV?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@std@@$00@?$_Variant_dispatcher@U?$integer_sequence@_K$0A@@std@@@std@@SAPEBD$$QEAV_lambda_614acedd3816982923c7fef7d309115d_@@AEAV?$variant@U?$pair@PEBD_K@std@@V?$vector@DV?$allocator@D@std@@@2@@1@@Z; std::_Variant_dispatcher<std::integer_sequence<unsigned __int64,0>>::_Dispatch2<char const *,_lambda_614acedd3816982923c7fef7d309115d_,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>> &,1>(_lambda_614acedd3816982923c7fef7d309115d_ &&,std::variant<std::pair<char const *,unsigned __int64>,std::vector<char>> &)
```

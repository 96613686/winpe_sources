# DeleteCorruptFiles(ulong)

- ea: `0x1800a7180`
- end: `0x1800a73a2`
- name: `?DeleteCorruptFiles@@YAJK@Z`
- size: `546`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180042d04`
- `0x1800433f4`
- `0x1800436c0`
- `0x1800b0bcc`

## callees

- `0x180009b00`
- `0x18001c800`
- `0x18005bb90`
- `0x180062204`
- `0x180080fb0`
- `0x1800810a4`
- `0x1800a7180`
- `0x1800b3848`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a725b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a725b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7316`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a728d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a7347`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a728d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a7347`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a724e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a730a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a724e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a730a`

## pseudocode

```c
__int64 __fastcall DeleteCorruptFiles(unsigned int a1)
{
  unsigned int v1; // edi
  int v2; // r15d
  const char *v3; // r9
  signed int IndexedDBFilePath; // ebx
  void *v5; // rsi
  WCHAR *v6; // r14
  BOOL v7; // r12d
  unsigned int i; // r13d
  signed int LastError; // eax
  BOOL v10; // esi
  unsigned int j; // edi
  signed int v12; // eax
  LPCWSTR lpFileName; // [rsp+20h] [rbp-68h] BYREF
  void *Block; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v16[32]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v1 = a1;
  LODWORD(Block) = a1;
  v2 = a1 & 0x40;
  LODWORD(lpFileName) = v2;
  if ( (a1 & 0x40) != 0 )
  {
    try
    {
      ClientIdentity::s_GetPackageName((__int64)v16);
      ScheduleQuotaRecalculation(v16, (v1 >> 1) & 1);
      std::wstring::~wstring(v16);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x3B,
        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\ese\\eselayerutils.cxx",
        v3);
      v1 = (unsigned int)Block;
      v2 = (int)lpFileName;
    }
  }
  Block = 0;
  lpFileName = 0;
  IndexedDBFilePath = GetIndexedDBFilePath(v1, 0, (unsigned __int16 **)&Block, (unsigned __int16 **)&lpFileName);
  v5 = Block;
  if ( IndexedDBFilePath < 0 )
  {
    v6 = (WCHAR *)lpFileName;
  }
  else
  {
    IndexedDBFilePath = DeleteDatabaseLogFiles((const unsigned __int16 *)Block);
    v6 = (WCHAR *)lpFileName;
    if ( IndexedDBFilePath >= 0 )
    {
      IndexedDBFilePath = 0;
      v7 = 0;
      for ( i = 0; i < 2 && !v7; ++i )
      {
        v7 = DeleteFileW(v6);
        if ( !v7 )
        {
          LastError = GetLastError();
          IndexedDBFilePath = LastError;
          if ( LastError > 0 )
            IndexedDBFilePath = (unsigned __int16)LastError | 0x80070000;
          if ( (unsigned int)(IndexedDBFilePath + 2147024894) <= 1 )
          {
            IndexedDBFilePath = 0;
            break;
          }
          if ( IndexedDBFilePath < 0 && i + 1 < 2 )
            Sleep(0xBB8u);
        }
      }
      if ( (v1 & 0x10) == 0 && !v2 )
      {
        operator delete(v5);
        Block = 0;
        operator delete(v6);
        lpFileName = 0;
        if ( IndexedDBFilePath < 0 )
          return (unsigned int)IndexedDBFilePath;
        IndexedDBFilePath = GetIndexedDBFilePath(
                              v1 ^ 8,
                              0,
                              (unsigned __int16 **)&Block,
                              (unsigned __int16 **)&lpFileName);
        v6 = (WCHAR *)lpFileName;
        if ( IndexedDBFilePath >= 0 )
        {
          IndexedDBFilePath = 0;
          v10 = 0;
          for ( j = 0; j < 2 && !v10; ++j )
          {
            v10 = DeleteFileW(v6);
            if ( !v10 )
            {
              v12 = GetLastError();
              IndexedDBFilePath = v12;
              if ( v12 > 0 )
                IndexedDBFilePath = (unsigned __int16)v12 | 0x80070000;
              if ( (unsigned int)(IndexedDBFilePath + 2147024894) <= 1 )
              {
                IndexedDBFilePath = 0;
                break;
              }
              if ( IndexedDBFilePath < 0 && j + 1 < 2 )
                Sleep(0xBB8u);
            }
          }
        }
        v5 = Block;
      }
    }
  }
  if ( v5 )
    operator delete(v5);
  if ( v6 )
    operator delete(v6);
  return (unsigned int)IndexedDBFilePath;
}

```

## disassembly

```asm
0x1800a7180  mov     [rsp+arg_8], rbx
0x1800a7185  mov     [rsp+arg_10], rsi
0x1800a718a  push    rdi
0x1800a718b  push    r12
0x1800a718d  push    r13
0x1800a718f  push    r14
0x1800a7191  push    r15
0x1800a7193  sub     rsp, 60h
0x1800a7197  mov     rax, cs:__security_cookie
0x1800a719e  xor     rax, rsp
0x1800a71a1  mov     [rsp+88h+var_38], rax
0x1800a71a6  mov     edi, ecx
0x1800a71a8  mov     dword ptr [rsp+88h+Block], ecx
0x1800a71ac  mov     r15d, ecx
0x1800a71af  and     r15d, 40h
0x1800a71b3  mov     dword ptr [rsp+88h+lpFileName], r15d
0x1800a71b8  jz      short loc_1800A71ED
0x1800a71ba  lea     rcx, [rsp+88h+var_58]
0x1800a71bf  call    ?s_GetPackageName@ClientIdentity@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ClientIdentity::s_GetPackageName(void)
0x1800a71c4  nop
0x1800a71c5  mov     edx, edi
0x1800a71c7  shr     edx, 1
0x1800a71c9  and     edx, 1
0x1800a71cc  lea     rcx, [rsp+88h+var_58]
0x1800a71d1  call    ?ScheduleQuotaRecalculation@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4WebPlatStorageHandlerType@@@Z; ScheduleQuotaRecalculation(std::wstring const &,WebPlatStorageHandlerType)
0x1800a71d6  nop
0x1800a71d7  lea     rcx, [rsp+88h+var_58]; void *
0x1800a71dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a71e1  nop
0x1800a71e2  jmp     short loc_1800A71ED
0x1800a71e4  mov     edi, dword ptr [rsp+88h+Block]
0x1800a71e8  mov     r15d, dword ptr [rsp+88h+lpFileName]
0x1800a71ed  mov     [rsp+88h+Block], 0
0x1800a71f6  mov     [rsp+88h+lpFileName], 0
0x1800a71ff  lea     r9, [rsp+88h+lpFileName]; unsigned __int16 **
0x1800a7204  lea     r8, [rsp+88h+Block]; unsigned __int16 **
0x1800a7209  xor     edx, edx; bool
0x1800a720b  mov     ecx, edi; unsigned int
0x1800a720d  call    ?GetIndexedDBFilePath@@YAJK_NPEAPEAG1@Z; GetIndexedDBFilePath(ulong,bool,ushort * *,ushort * *)
0x1800a7212  mov     ebx, eax
0x1800a7214  mov     rsi, [rsp+88h+Block]
0x1800a7219  test    eax, eax
0x1800a721b  js      loc_1800A735A
0x1800a7221  mov     rcx, rsi; unsigned __int16 *
0x1800a7224  call    ?DeleteDatabaseLogFiles@@YAJPEBG@Z; DeleteDatabaseLogFiles(ushort const *)
0x1800a7229  mov     ebx, eax
0x1800a722b  mov     r14, [rsp+88h+lpFileName]
0x1800a7230  test    eax, eax
0x1800a7232  js      loc_1800A735F
0x1800a7238  xor     ebx, ebx
0x1800a723a  xor     r12d, r12d
0x1800a723d  xor     r13d, r13d
0x1800a7240  cmp     r13d, 2
0x1800a7244  jnb     short loc_1800A729A
0x1800a7246  test    r12d, r12d
0x1800a7249  jnz     short loc_1800A729A
0x1800a724b  mov     rcx, r14; lpFileName
0x1800a724e  call    cs:__imp_DeleteFileW
0x1800a7254  mov     r12d, eax
0x1800a7257  test    eax, eax
0x1800a7259  jnz     short loc_1800A7293
0x1800a725b  call    cs:__imp_GetLastError
0x1800a7261  mov     ebx, eax
0x1800a7263  test    eax, eax
0x1800a7265  jle     short loc_1800A7270
0x1800a7267  movzx   ebx, ax
0x1800a726a  or      ebx, 80070000h
0x1800a7270  lea     eax, [rbx+7FF8FFFEh]
0x1800a7276  cmp     eax, 1
0x1800a7279  jbe     short loc_1800A7298
0x1800a727b  test    ebx, ebx
0x1800a727d  jns     short loc_1800A7293
0x1800a727f  lea     eax, [r13+1]
0x1800a7283  cmp     eax, 2
0x1800a7286  jnb     short loc_1800A7293
0x1800a7288  mov     ecx, 0BB8h; dwMilliseconds
0x1800a728d  call    cs:__imp_Sleep
0x1800a7293  inc     r13d
0x1800a7296  jmp     short loc_1800A7240
0x1800a7298  xor     ebx, ebx
0x1800a729a  test    dil, 10h
0x1800a729e  jnz     loc_1800A735F
0x1800a72a4  test    r15d, r15d
0x1800a72a7  jnz     loc_1800A735F
0x1800a72ad  mov     rcx, rsi; Block
0x1800a72b0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a72b5  mov     [rsp+88h+Block], 0
0x1800a72be  mov     rcx, r14; Block
0x1800a72c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a72c6  mov     [rsp+88h+lpFileName], 0
0x1800a72cf  test    ebx, ebx
0x1800a72d1  js      loc_1800A7379
0x1800a72d7  xor     edi, 8
0x1800a72da  lea     r9, [rsp+88h+lpFileName]; unsigned __int16 **
0x1800a72df  lea     r8, [rsp+88h+Block]; unsigned __int16 **
0x1800a72e4  xor     edx, edx; bool
0x1800a72e6  mov     ecx, edi; unsigned int
0x1800a72e8  call    ?GetIndexedDBFilePath@@YAJK_NPEAPEAG1@Z; GetIndexedDBFilePath(ulong,bool,ushort * *,ushort * *)
0x1800a72ed  mov     ebx, eax
0x1800a72ef  mov     r14, [rsp+88h+lpFileName]
0x1800a72f4  test    eax, eax
0x1800a72f6  js      short loc_1800A7353
0x1800a72f8  xor     ebx, ebx
0x1800a72fa  xor     esi, esi
0x1800a72fc  xor     edi, edi
0x1800a72fe  cmp     edi, 2
0x1800a7301  jnb     short loc_1800A7353
0x1800a7303  test    esi, esi
0x1800a7305  jnz     short loc_1800A7353
0x1800a7307  mov     rcx, r14; lpFileName
0x1800a730a  call    cs:__imp_DeleteFileW
0x1800a7310  mov     esi, eax
0x1800a7312  test    eax, eax
0x1800a7314  jnz     short loc_1800A734D
0x1800a7316  call    cs:__imp_GetLastError
0x1800a731c  mov     ebx, eax
0x1800a731e  test    eax, eax
0x1800a7320  jle     short loc_1800A732B
0x1800a7322  movzx   ebx, ax
0x1800a7325  or      ebx, 80070000h
0x1800a732b  lea     eax, [rbx+7FF8FFFEh]
0x1800a7331  cmp     eax, 1
0x1800a7334  jbe     short loc_1800A7351
0x1800a7336  test    ebx, ebx
0x1800a7338  jns     short loc_1800A734D
0x1800a733a  lea     eax, [rdi+1]
0x1800a733d  cmp     eax, 2
0x1800a7340  jnb     short loc_1800A734D
0x1800a7342  mov     ecx, 0BB8h; dwMilliseconds
0x1800a7347  call    cs:__imp_Sleep
0x1800a734d  inc     edi
0x1800a734f  jmp     short loc_1800A72FE
0x1800a7351  xor     ebx, ebx
0x1800a7353  mov     rsi, [rsp+88h+Block]
0x1800a7358  jmp     short loc_1800A735F
0x1800a735a  mov     r14, [rsp+88h+lpFileName]
0x1800a735f  test    rsi, rsi
0x1800a7362  jz      short loc_1800A736C
0x1800a7364  mov     rcx, rsi; Block
0x1800a7367  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a736c  test    r14, r14
0x1800a736f  jz      short loc_1800A7379
0x1800a7371  mov     rcx, r14; Block
0x1800a7374  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a7379  mov     eax, ebx
0x1800a737b  mov     rcx, [rsp+88h+var_38]
0x1800a7380  xor     rcx, rsp; StackCookie
0x1800a7383  call    __security_check_cookie
0x1800a7388  lea     r11, [rsp+88h+var_28]
0x1800a738d  mov     rbx, [r11+38h]
0x1800a7391  mov     rsi, [r11+40h]
0x1800a7395  mov     rsp, r11
0x1800a7398  pop     r15
0x1800a739a  pop     r14
0x1800a739c  pop     r13
0x1800a739e  pop     r12
0x1800a73a0  pop     rdi
0x1800a73a1  retn
```

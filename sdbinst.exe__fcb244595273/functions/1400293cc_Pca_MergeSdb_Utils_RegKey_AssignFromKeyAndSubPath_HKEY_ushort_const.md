# Pca::MergeSdb::Utils::RegKey::AssignFromKeyAndSubPath(HKEY__ *,ushort const *)

- ea: `0x1400293cc`
- end: `0x140029553`
- name: `?AssignFromKeyAndSubPath@RegKey@Utils@MergeSdb@Pca@@QEAAKPEAUHKEY__@@PEBG@Z`
- size: `391`
- prototype: `__int64 __fastcall(HKEY *this, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400230fc`
- `0x140027c80`

## callees

- `0x140028350`
- `0x1400293cc`
- `0x14002c15c`
- `0x14002de74`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14002943d`
- `ADVAPI32!RegOpenKeyExW` at `0x14002943d`
- `ADVAPI32!RegCloseKey` at `0x140029414`
- `ADVAPI32!RegCloseKey` at `0x1400294ec`
- `ADVAPI32!RegCloseKey` at `0x140029414`
- `ADVAPI32!RegCloseKey` at `0x1400294ec`
- `KERNEL32!GetLastError` at `0x140029409`
- `KERNEL32!GetLastError` at `0x1400294ae`
- `KERNEL32!GetLastError` at `0x1400294e1`
- `KERNEL32!GetLastError` at `0x140029409`
- `KERNEL32!GetLastError` at `0x1400294ae`
- `KERNEL32!GetLastError` at `0x1400294e1`
- `KERNEL32!GetProcessHeap` at `0x140029472`
- `KERNEL32!GetProcessHeap` at `0x1400294b6`
- `KERNEL32!GetProcessHeap` at `0x140029511`
- `KERNEL32!GetProcessHeap` at `0x140029472`
- `KERNEL32!GetProcessHeap` at `0x1400294b6`
- `KERNEL32!GetProcessHeap` at `0x140029511`
- `KERNEL32!SetLastError` at `0x14002941c`
- `KERNEL32!SetLastError` at `0x1400294cc`
- `KERNEL32!SetLastError` at `0x1400294f4`
- `KERNEL32!SetLastError` at `0x14002941c`
- `KERNEL32!SetLastError` at `0x1400294cc`
- `KERNEL32!SetLastError` at `0x1400294f4`
- `KERNEL32!HeapFree` at `0x140029480`
- `KERNEL32!HeapFree` at `0x1400294c4`
- `KERNEL32!HeapFree` at `0x14002951f`
- `KERNEL32!HeapFree` at `0x140029480`
- `KERNEL32!HeapFree` at `0x1400294c4`
- `KERNEL32!HeapFree` at `0x14002951f`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegKey::AssignFromKeyAndSubPath(
        HKEY *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  HKEY *v6; // rsi
  HKEY v7; // r14
  DWORD LastError; // ebx
  unsigned int v9; // r14d
  __int64 v10; // r8
  void *v11; // rbx
  HANDLE ProcessHeap; // rax
  HKEY v14; // rbp
  DWORD v15; // ebx
  HANDLE v16; // rax
  HKEY v17; // rbp
  DWORD v18; // ebx
  void *v19; // rbx
  HANDLE v20; // rax
  LPVOID lpMem; // [rsp+68h] [rbp+10h] BYREF
  const unsigned __int16 *v22; // [rsp+70h] [rbp+18h] BYREF

  v22 = a3;
  Pca::MergeSdb::Utils::RegKey::Reset((Pca::MergeSdb::Utils::RegKey *)this);
  if ( (unsigned __int64)a2 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return 87;
  v6 = this + 1;
  v7 = this[1];
  if ( v7 )
  {
    LastError = GetLastError();
    RegCloseKey(v7);
    SetLastError(LastError);
  }
  *v6 = 0;
  v9 = RegOpenKeyExW(a2, a3, 0, 0x20019u, this + 1);
  if ( v9 )
  {
    lpMem = 0;
    if ( (unsigned int)Pca::MergeSdb::Utils::RegUtil::KeyPathFromHKey(&lpMem, a2) )
    {
      v11 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v11);
      }
      return 6;
    }
    else
    {
      if ( (int)wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short [2],unsigned short const *>(
                  this,
                  &lpMem,
                  v10,
                  &v22) < 0 )
      {
        v14 = *this;
        if ( *this )
        {
          v15 = GetLastError();
          v16 = GetProcessHeap();
          HeapFree(v16, 0, v14);
          SetLastError(v15);
        }
        *this = 0;
      }
      v17 = *v6;
      if ( *v6 )
      {
        v18 = GetLastError();
        RegCloseKey(v17);
        SetLastError(v18);
      }
      *v6 = 0;
      *((_WORD *)this + 8) = 256;
      v19 = lpMem;
      if ( lpMem )
      {
        v20 = GetProcessHeap();
        HeapFree(v20, 0, v19);
      }
      return v9;
    }
  }
  else
  {
    *((_WORD *)this + 8) = 257;
    return Pca::MergeSdb::Utils::RegUtil::KeyPathFromHKey(this, *v6);
  }
}

```

## disassembly

```asm
0x1400293cc  mov     [rsp+arg_0], rbx
0x1400293d1  mov     [rsp+arg_10], r8
0x1400293d6  push    rbp
0x1400293d7  push    rsi
0x1400293d8  push    rdi
0x1400293d9  push    r14
0x1400293db  push    r15
0x1400293dd  sub     rsp, 30h
0x1400293e1  mov     r15, r8
0x1400293e4  mov     rbp, rdx
0x1400293e7  mov     rdi, rcx
0x1400293ea  call    ?Reset@RegKey@Utils@MergeSdb@Pca@@QEAAXXZ; Pca::MergeSdb::Utils::RegKey::Reset(void)
0x1400293ef  lea     rax, [rbp-1]
0x1400293f3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400293f7  ja      loc_14002953D
0x1400293fd  lea     rsi, [rdi+8]
0x140029401  mov     r14, [rsi]
0x140029404  test    r14, r14
0x140029407  jz      short loc_140029422
0x140029409  call    cs:__imp_GetLastError
0x14002940f  mov     ebx, eax
0x140029411  mov     rcx, r14; hKey
0x140029414  call    cs:__imp_RegCloseKey
0x14002941a  mov     ecx, ebx; dwErrCode
0x14002941c  call    cs:__imp_SetLastError
0x140029422  mov     qword ptr [rsi], 0
0x140029429  mov     [rsp+58h+phkResult], rsi; phkResult
0x14002942e  mov     r9d, 20019h; samDesired
0x140029434  xor     r8d, r8d; ulOptions
0x140029437  mov     rdx, r15; lpSubKey
0x14002943a  mov     rcx, rbp; hKey
0x14002943d  call    cs:__imp_RegOpenKeyExW
0x140029443  mov     r14d, eax
0x140029446  test    eax, eax
0x140029448  jz      loc_14002952A
0x14002944e  mov     [rsp+58h+lpMem], 0
0x140029457  mov     rdx, rbp
0x14002945a  lea     rcx, [rsp+58h+lpMem]
0x14002945f  call    ?KeyPathFromHKey@RegUtil@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@@Z; Pca::MergeSdb::Utils::RegUtil::KeyPathFromHKey(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,HKEY__ *)
0x140029464  test    eax, eax
0x140029466  jz      short loc_140029490
0x140029468  mov     rbx, [rsp+58h+lpMem]
0x14002946d  test    rbx, rbx
0x140029470  jz      short loc_140029486
0x140029472  call    cs:__imp_GetProcessHeap
0x140029478  mov     rcx, rax; hHeap
0x14002947b  mov     r8, rbx; lpMem
0x14002947e  xor     edx, edx; dwFlags
0x140029480  call    cs:__imp_HeapFree
0x140029486  mov     eax, 6
0x14002948b  jmp     loc_140029542
0x140029490  lea     r9, [rsp+58h+arg_10]
0x140029495  lea     rdx, [rsp+58h+lpMem]
0x14002949a  mov     rcx, rdi
0x14002949d  call    ??$str_concat_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@$$BY01GPEBG@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV10@AEAY01$$CBGAEBQEBG@Z; wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ushort [2],ushort const *>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,ushort const (&)[2],ushort const * const &)
0x1400294a2  test    eax, eax
0x1400294a4  jns     short loc_1400294D9
0x1400294a6  mov     rbp, [rdi]
0x1400294a9  test    rbp, rbp
0x1400294ac  jz      short loc_1400294D2
0x1400294ae  call    cs:__imp_GetLastError
0x1400294b4  mov     ebx, eax
0x1400294b6  call    cs:__imp_GetProcessHeap
0x1400294bc  mov     rcx, rax; hHeap
0x1400294bf  mov     r8, rbp; lpMem
0x1400294c2  xor     edx, edx; dwFlags
0x1400294c4  call    cs:__imp_HeapFree
0x1400294ca  mov     ecx, ebx; dwErrCode
0x1400294cc  call    cs:__imp_SetLastError
0x1400294d2  mov     qword ptr [rdi], 0
0x1400294d9  mov     rbp, [rsi]
0x1400294dc  test    rbp, rbp
0x1400294df  jz      short loc_1400294FA
0x1400294e1  call    cs:__imp_GetLastError
0x1400294e7  mov     ebx, eax
0x1400294e9  mov     rcx, rbp; hKey
0x1400294ec  call    cs:__imp_RegCloseKey
0x1400294f2  mov     ecx, ebx; dwErrCode
0x1400294f4  call    cs:__imp_SetLastError
0x1400294fa  mov     qword ptr [rsi], 0
0x140029501  mov     word ptr [rdi+10h], 100h
0x140029507  mov     rbx, [rsp+58h+lpMem]
0x14002950c  test    rbx, rbx
0x14002950f  jz      short loc_140029525
0x140029511  call    cs:__imp_GetProcessHeap
0x140029517  mov     rcx, rax; hHeap
0x14002951a  mov     r8, rbx; lpMem
0x14002951d  xor     edx, edx; dwFlags
0x14002951f  call    cs:__imp_HeapFree
0x140029525  mov     eax, r14d
0x140029528  jmp     short loc_140029542
0x14002952a  mov     word ptr [rdi+10h], 101h
0x140029530  mov     rdx, [rsi]
0x140029533  mov     rcx, rdi
0x140029536  call    ?KeyPathFromHKey@RegUtil@Utils@MergeSdb@Pca@@SAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@@Z; Pca::MergeSdb::Utils::RegUtil::KeyPathFromHKey(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,HKEY__ *)
0x14002953b  jmp     short loc_140029542
0x14002953d  mov     eax, 57h ; 'W'
0x140029542  mov     rbx, [rsp+58h+arg_0]
0x140029547  add     rsp, 30h
0x14002954b  pop     r15
0x14002954d  pop     r14
0x14002954f  pop     rdi
0x140029550  pop     rsi
0x140029551  pop     rbp
0x140029552  retn
```

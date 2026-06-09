# CFSFolder::Initialize(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180185710`
- end: `0x1801859a6`
- name: `?Initialize@CFSFolder@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `662`
- prototype: `int(CFSFolder *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180185710`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180185887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180185987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180185887`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180185987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180185735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180185968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180185735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180185968`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180185768`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180185768`
- `OLEAUT32!__imp_SysFreeString` at `0x1801857e7`
- `OLEAUT32!__imp_SysFreeString` at `0x180185841`
- `OLEAUT32!__imp_SysFreeString` at `0x1801857e7`
- `OLEAUT32!__imp_SysFreeString` at `0x180185841`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801858bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801858bb`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1801858e1`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1801858e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018574b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180185782`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018579c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801857cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180185979`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018574b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180185782`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018579c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801857cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180185979`

## pseudocode

```c
__int64 __fastcall CFSFolder::Initialize(CFSFolder *this, const struct _ITEMIDLIST_ABSOLUTE *a2)
{
  DWORD LastError; // r14d
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  bool v8; // zf
  OLECHAR *v9; // rcx
  void *v10; // rsi
  OLECHAR *v11; // rcx
  __int64 v12; // rcx
  const struct _ITEMIDLIST_ABSOLUTE *v13; // rdx
  unsigned int v14; // r8d
  __int64 v15; // rcx
  size_t v16; // rsi
  void *v17; // rdi
  size_t v18; // r14
  __int64 result; // rax
  DWORD v20; // edi
  LPMALLOC ppMalloc; // [rsp+20h] [rbp-38h] BYREF

  LastError = GetLastError();
  CoTaskMemFree(*((LPVOID *)this + 45));
  v5 = (void *)*((_QWORD *)this + 49);
  *((_QWORD *)this + 45) = 0;
  LocalFree(v5);
  v6 = (void *)*((_QWORD *)this + 50);
  *((_QWORD *)this + 49) = 0;
  CoTaskMemFree(v6);
  v7 = (void *)*((_QWORD *)this + 51);
  *((_QWORD *)this + 50) = 0;
  CoTaskMemFree(v7);
  v8 = (*((_BYTE *)this + 464) & 0x10) == 0;
  *((_QWORD *)this + 51) = 0;
  *((_DWORD *)this + 104) = -2;
  if ( v8 )
  {
    CoTaskMemFree(*((LPVOID *)this + 46));
    v9 = (OLECHAR *)*((_QWORD *)this + 47);
    *((_QWORD *)this + 46) = 0;
    SysFreeString(v9);
    *((_QWORD *)this + 47) = 0;
    v10 = (void *)*((_QWORD *)this + 48);
    if ( v10 )
    {
      v20 = GetLastError();
      CoTaskMemFree(v10);
      SetLastError(v20);
    }
    *((_QWORD *)this + 48) = 0;
    *((_DWORD *)this + 116) &= ~0x200u;
    v11 = (OLECHAR *)*((_QWORD *)this + 57);
    *((_DWORD *)this + 105) = -1;
    *((_DWORD *)this + 112) = 0;
    *(GUID *)((char *)this + 424) = GUID_NULL;
    SysFreeString(v11);
    *((_QWORD *)this + 57) = 0;
  }
  v12 = *((_QWORD *)this + 69);
  *((_QWORD *)this + 69) = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 12) + 24LL))((char *)this + 96);
  SetLastError(LastError);
  if ( a2 )
  {
    v13 = a2;
    v14 = 2;
    do
    {
      v15 = *(unsigned __int16 *)v13;
      if ( !(_WORD)v15 )
        break;
      v14 += v15;
      v13 = (const struct _ITEMIDLIST_ABSOLUTE *)((char *)v13 + v15);
    }
    while ( v13 );
    v16 = v14;
    v17 = CoTaskMemAlloc(v14);
    if ( v17 )
    {
      ppMalloc = 0;
      v18 = 0;
      if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
      {
        v18 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v17);
        ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
      }
      memset_0(v17, 0, v18);
      memcpy_0(v17, a2, v16);
    }
    *((_QWORD *)this + 45) = v17;
    result = 0;
    if ( !v17 )
      return 2147942414LL;
  }
  else
  {
    *((_QWORD *)this + 45) = 0;
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180185710  mov     [rsp+arg_10], rbx
0x180185715  push    rbp
0x180185716  push    rsi
0x180185717  push    rdi
0x180185718  push    r14
0x18018571a  push    r15
0x18018571c  sub     rsp, 30h
0x180185720  mov     rax, cs:__security_cookie
0x180185727  xor     rax, rsp
0x18018572a  mov     [rsp+58h+var_30], rax
0x18018572f  mov     rbp, rdx
0x180185732  mov     rbx, rcx
0x180185735  call    cs:__imp_GetLastError
0x18018573c  nop     dword ptr [rax+rax+00h]
0x180185741  mov     rcx, [rbx+168h]; pv
0x180185748  mov     r14d, eax
0x18018574b  call    cs:__imp_CoTaskMemFree
0x180185752  nop     dword ptr [rax+rax+00h]
0x180185757  mov     rcx, [rbx+188h]; hMem
0x18018575e  xor     r15d, r15d
0x180185761  mov     [rbx+168h], r15
0x180185768  call    cs:__imp_LocalFree
0x18018576f  nop     dword ptr [rax+rax+00h]
0x180185774  mov     rcx, [rbx+190h]; pv
0x18018577b  mov     [rbx+188h], r15
0x180185782  call    cs:__imp_CoTaskMemFree
0x180185789  nop     dword ptr [rax+rax+00h]
0x18018578e  mov     rcx, [rbx+198h]; pv
0x180185795  mov     [rbx+190h], r15
0x18018579c  call    cs:__imp_CoTaskMemFree
0x1801857a3  nop     dword ptr [rax+rax+00h]
0x1801857a8  test    byte ptr [rbx+1D0h], 10h
0x1801857af  mov     [rbx+198h], r15
0x1801857b6  mov     dword ptr [rbx+1A0h], 0FFFFFFFEh
0x1801857c0  jnz     loc_180185854
0x1801857c6  mov     rcx, [rbx+170h]; pv
0x1801857cd  call    cs:__imp_CoTaskMemFree
0x1801857d4  nop     dword ptr [rax+rax+00h]
0x1801857d9  mov     rcx, [rbx+178h]; bstrString
0x1801857e0  mov     [rbx+170h], r15
0x1801857e7  call    cs:__imp_SysFreeString
0x1801857ee  nop     dword ptr [rax+rax+00h]
0x1801857f3  mov     [rbx+178h], r15
0x1801857fa  mov     rsi, [rbx+180h]
0x180185801  test    rsi, rsi
0x180185804  jnz     loc_180185968
0x18018580a  mov     [rbx+180h], r15
0x180185811  and     dword ptr [rbx+1D0h], 0FFFFFDFFh
0x18018581b  mov     rcx, [rbx+1C8h]; bstrString
0x180185822  mov     dword ptr [rbx+1A4h], 0FFFFFFFFh
0x18018582c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180185833  mov     [rbx+1C0h], r15d
0x18018583a  movups  xmmword ptr [rbx+1A8h], xmm0
0x180185841  call    cs:__imp_SysFreeString
0x180185848  nop     dword ptr [rax+rax+00h]
0x18018584d  mov     [rbx+1C8h], r15
0x180185854  mov     rcx, [rbx+228h]
0x18018585b  mov     [rbx+228h], r15
0x180185862  test    rcx, rcx
0x180185865  jz      short loc_180185873
0x180185867  mov     rax, [rcx]
0x18018586a  mov     rax, [rax+10h]
0x18018586e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185873  mov     rax, [rbx+60h]
0x180185877  lea     rcx, [rbx+60h]
0x18018587b  mov     rax, [rax+18h]
0x18018587f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185884  mov     ecx, r14d; dwErrCode
0x180185887  call    cs:__imp_SetLastError
0x18018588e  nop     dword ptr [rax+rax+00h]
0x180185893  test    rbp, rbp
0x180185896  jz      loc_180185998
0x18018589c  mov     rdx, rbp
0x18018589f  mov     r8d, 2
0x1801858a5  movzx   ecx, word ptr [rdx]
0x1801858a8  test    cx, cx
0x1801858ab  jz      short loc_1801858B5
0x1801858ad  add     r8d, ecx
0x1801858b0  add     rdx, rcx
0x1801858b3  jnz     short loc_1801858A5
0x1801858b5  mov     ecx, r8d; cb
0x1801858b8  mov     esi, r8d
0x1801858bb  call    cs:__imp_CoTaskMemAlloc
0x1801858c2  nop     dword ptr [rax+rax+00h]
0x1801858c7  mov     rdi, rax
0x1801858ca  test    rax, rax
0x1801858cd  jz      short loc_180185934
0x1801858cf  lea     rdx, [rsp+58h+ppMalloc]; ppMalloc
0x1801858d4  mov     [rsp+58h+ppMalloc], r15
0x1801858d9  mov     ecx, 1; dwMemContext
0x1801858de  mov     r14, r15
0x1801858e1  call    cs:__imp_CoGetMalloc
0x1801858e8  nop     dword ptr [rax+rax+00h]
0x1801858ed  test    eax, eax
0x1801858ef  js      short loc_180185919
0x1801858f1  mov     rcx, [rsp+58h+ppMalloc]
0x1801858f6  mov     rdx, [rcx]
0x1801858f9  mov     rax, [rdx+30h]
0x1801858fd  mov     rdx, rdi
0x180185900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185905  mov     rcx, [rsp+58h+ppMalloc]
0x18018590a  mov     r14, rax
0x18018590d  mov     r9, [rcx]
0x180185910  mov     rax, [r9+10h]
0x180185914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180185919  mov     r8, r14; Size
0x18018591c  xor     edx, edx; Val
0x18018591e  mov     rcx, rdi; void *
0x180185921  call    memset_0
0x180185926  mov     r8, rsi; Size
0x180185929  mov     rdx, rbp; Src
0x18018592c  mov     rcx, rdi; void *
0x18018592f  call    memcpy_0
0x180185934  test    rdi, rdi
0x180185937  mov     [rbx+168h], rdi
0x18018593e  mov     eax, r15d
0x180185941  mov     ecx, 8007000Eh
0x180185946  cmovz   eax, ecx
0x180185949  mov     rcx, [rsp+58h+var_30]
0x18018594e  xor     rcx, rsp; StackCookie
0x180185951  call    __security_check_cookie
0x180185956  mov     rbx, [rsp+58h+arg_10]
0x18018595b  add     rsp, 30h
0x18018595f  pop     r15
0x180185961  pop     r14
0x180185963  pop     rdi
0x180185964  pop     rsi
0x180185965  pop     rbp
0x180185966  retn
0x180185968  call    cs:__imp_GetLastError
0x18018596f  nop     dword ptr [rax+rax+00h]
0x180185974  mov     rcx, rsi; pv
0x180185977  mov     edi, eax
0x180185979  call    cs:__imp_CoTaskMemFree
0x180185980  nop     dword ptr [rax+rax+00h]
0x180185985  mov     ecx, edi; dwErrCode
0x180185987  call    cs:__imp_SetLastError
0x18018598e  nop     dword ptr [rax+rax+00h]
0x180185993  jmp     loc_18018580A
0x180185998  mov     [rbx+168h], r15
0x18018599f  mov     eax, 80070057h
0x1801859a4  jmp     short loc_180185949
```

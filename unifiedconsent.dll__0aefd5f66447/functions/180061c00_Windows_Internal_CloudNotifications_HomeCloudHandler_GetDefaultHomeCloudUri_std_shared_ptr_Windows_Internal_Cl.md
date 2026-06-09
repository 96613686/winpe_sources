# Windows::Internal::CloudNotifications::HomeCloudHandler::GetDefaultHomeCloudUri(std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>)

- ea: `0x180061c00`
- end: `0x180061d02`
- name: `?GetDefaultHomeCloudUri@HomeCloudHandler@CloudNotifications@Internal@Windows@@AEAA?AUhstring@winrt@@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@Z`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800630b0`

## callees

- `0x18000ebfc`
- `0x18000f44c`
- `0x180061c00`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180061c56`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180061c56`

## string_xrefs

- `0x180061c5c`: `https://activity.windows.com/`
- `0x180061c63`: `https://ppe.activity.windows.com/`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct winrt::impl::shared_hstring_header **__fastcall Windows::Internal::CloudNotifications::HomeCloudHandler::GetDefaultHomeCloudUri(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  const WCHAR *v6; // rcx
  unsigned int v7; // edx
  const wchar_t *v8; // r14
  __int64 v9; // rbx
  struct winrt::impl::shared_hstring_header *v10; // rbp
  volatile signed __int32 *v11; // rbx

  v5 = *(_QWORD *)(*a3 + 8LL);
  if ( v5 )
    v6 = *(const WCHAR **)(v5 + 16);
  else
    v6 = &Name;
  v8 = L"https://ppe.activity.windows.com/";
  if ( CompareStringOrdinal(v6, -1, L"ppe", -1, 1) != 2 )
    v8 = L"https://activity.windows.com/";
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  if ( (_DWORD)v9 )
  {
    v10 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v9, v7);
    memcpy_s((char *)v10 + 28, 2LL * (unsigned int)v9, v8, 2LL * (unsigned int)v9);
  }
  else
  {
    v10 = 0;
  }
  *a2 = v10;
  v11 = (volatile signed __int32 *)a3[1];
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180061c00  mov     [rsp+arg_0], rbx
0x180061c05  mov     [rsp+arg_8], rbp
0x180061c0a  mov     [rsp+arg_10], r8
0x180061c0f  push    rsi
0x180061c10  push    rdi
0x180061c11  push    r12
0x180061c13  push    r14
0x180061c15  push    r15
0x180061c17  sub     rsp, 40h
0x180061c1b  mov     rsi, r8
0x180061c1e  mov     rdi, rdx
0x180061c21  xor     r15d, r15d
0x180061c24  mov     rax, [r8]
0x180061c27  mov     rcx, [rax+8]
0x180061c2b  test    rcx, rcx
0x180061c2e  jz      short loc_180061C36
0x180061c30  mov     rcx, [rcx+10h]
0x180061c34  jmp     short loc_180061C3D
0x180061c36  lea     rcx, Name; lpString1
0x180061c3d  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180061c45  or      r12, 0FFFFFFFFFFFFFFFFh
0x180061c49  mov     r9d, r12d; cchCount2
0x180061c4c  lea     r8, aPpe; "ppe"
0x180061c53  mov     edx, r12d; cchCount1
0x180061c56  call    cs:__imp_CompareStringOrdinal
0x180061c5c  lea     rcx, aHttpsActivityW; "https://activity.windows.com/"
0x180061c63  lea     r14, aHttpsPpeActivi; "https://ppe.activity.windows.com/"
0x180061c6a  cmp     eax, 2
0x180061c6d  cmovnz  r14, rcx
0x180061c71  mov     rbx, r12
0x180061c74  inc     rbx
0x180061c77  cmp     [r14+rbx*2], r15w
0x180061c7c  jnz     short loc_180061C74
0x180061c7e  test    ebx, ebx
0x180061c80  jnz     short loc_180061C87
0x180061c82  mov     rbp, r15
0x180061c85  jmp     short loc_180061CA5
0x180061c87  mov     ecx, ebx; this
0x180061c89  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180061c8e  mov     rbp, rax
0x180061c91  mov     edx, ebx
0x180061c93  add     rdx, rdx; DestinationSize
0x180061c96  lea     rcx, [rax+1Ch]; Destination
0x180061c9a  mov     r9, rdx; SourceSize
0x180061c9d  mov     r8, r14; Source
0x180061ca0  call    memcpy_s
0x180061ca5  mov     [rdi], rbp
0x180061ca8  mov     rbx, [rsi+8]
0x180061cac  test    rbx, rbx
0x180061caf  jz      short loc_180061CE8
0x180061cb1  mov     eax, r12d
0x180061cb4  lock xadd [rbx+8], eax
0x180061cb9  add     eax, r12d
0x180061cbc  jnz     short loc_180061CE8
0x180061cbe  mov     rax, [rbx]
0x180061cc1  mov     rcx, rbx
0x180061cc4  mov     rax, [rax]
0x180061cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ccc  mov     eax, r12d
0x180061ccf  lock xadd [rbx+0Ch], eax
0x180061cd4  add     eax, r12d
0x180061cd7  jnz     short loc_180061CE8
0x180061cd9  mov     rax, [rbx]
0x180061cdc  mov     rcx, rbx
0x180061cdf  mov     rax, [rax+8]
0x180061ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ce8  mov     rax, rdi
0x180061ceb  mov     rbx, [rsp+68h+arg_0]
0x180061cf0  mov     rbp, [rsp+68h+arg_8]
0x180061cf5  add     rsp, 40h
0x180061cf9  pop     r15
0x180061cfb  pop     r14
0x180061cfd  pop     r12
0x180061cff  pop     rdi
0x180061d00  pop     rsi
0x180061d01  retn
```

# CETWLogger::GetPropertyString(ushort const *,ushort * *)

- ea: `0x1800d9570`
- end: `0x1800d9615`
- name: `?GetPropertyString@CETWLogger@@UEAAJPEBGPEAPEAG@Z`
- size: `165`
- prototype: `int(CETWLogger *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800040b8`
- `0x180004306`
- `0x1800d9570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800d9602`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800d9602`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d959c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d95e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d959c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d95e0`

## pseudocode

```c
__int64 __fastcall CETWLogger::GetPropertyString(CETWLogger *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v6; // rax
  unsigned int v7; // ebx
  const IID *v8; // rcx
  unsigned __int16 *v9; // rax

  if ( !wcscmp_0(a2, L"ETWActivityID") )
  {
    v6 = (unsigned __int16 *)CoTaskMemAlloc(0x80u);
    *a3 = v6;
    if ( !v6 )
      return (unsigned int)-2147024882;
    memset_0(v6, 0, 0x80u);
    v8 = (const IID *)((char *)this + 80);
    return (unsigned int)StringFromIID(v8, a3);
  }
  v7 = 0;
  if ( wcscmp_0(a2, L"ETWProviderGUID") )
    return v7;
  v9 = (unsigned __int16 *)CoTaskMemAlloc(0x80u);
  *a3 = v9;
  if ( v9 )
  {
    memset_0(v9, 0, 0x80u);
    v8 = (const IID *)((char *)this + 96);
    return (unsigned int)StringFromIID(v8, a3);
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1800d9570  push    rbx
0x1800d9572  push    rbp
0x1800d9573  push    rsi
0x1800d9574  push    rdi
0x1800d9575  sub     rsp, 28h
0x1800d9579  mov     rsi, rdx
0x1800d957c  mov     rbp, rcx
0x1800d957f  mov     rcx, rsi; String1
0x1800d9582  lea     rdx, aEtwactivityid; "ETWActivityID"
0x1800d9589  mov     rdi, r8
0x1800d958c  call    wcscmp_0
0x1800d9591  test    eax, eax
0x1800d9593  jnz     short loc_1800D95C4
0x1800d9595  mov     ebx, 80h
0x1800d959a  mov     ecx, ebx; cb
0x1800d959c  call    cs:__imp_CoTaskMemAlloc
0x1800d95a2  mov     [rdi], rax
0x1800d95a5  test    rax, rax
0x1800d95a8  jnz     short loc_1800D95B1
0x1800d95aa  mov     ebx, 8007000Eh
0x1800d95af  jmp     short loc_1800D960A
0x1800d95b1  mov     r8, rbx; Size
0x1800d95b4  xor     edx, edx; Val
0x1800d95b6  mov     rcx, rax; void *
0x1800d95b9  call    memset_0
0x1800d95be  lea     rcx, [rbp+50h]
0x1800d95c2  jmp     short loc_1800D95FF
0x1800d95c4  lea     rdx, aEtwprovidergui; "ETWProviderGUID"
0x1800d95cb  mov     rcx, rsi; String1
0x1800d95ce  xor     ebx, ebx
0x1800d95d0  call    wcscmp_0
0x1800d95d5  test    eax, eax
0x1800d95d7  jnz     short loc_1800D960A
0x1800d95d9  mov     ebx, 80h
0x1800d95de  mov     ecx, ebx; cb
0x1800d95e0  call    cs:__imp_CoTaskMemAlloc
0x1800d95e6  mov     [rdi], rax
0x1800d95e9  test    rax, rax
0x1800d95ec  jz      short loc_1800D95AA
0x1800d95ee  mov     r8d, ebx; Size
0x1800d95f1  xor     edx, edx; Val
0x1800d95f3  mov     rcx, rax; void *
0x1800d95f6  call    memset_0
0x1800d95fb  lea     rcx, [rbp+60h]; rclsid
0x1800d95ff  mov     rdx, rdi; lplpsz
0x1800d9602  call    cs:__imp_StringFromIID
0x1800d9608  mov     ebx, eax
0x1800d960a  mov     eax, ebx
0x1800d960c  add     rsp, 28h
0x1800d9610  pop     rdi
0x1800d9611  pop     rsi
0x1800d9612  pop     rbp
0x1800d9613  pop     rbx
0x1800d9614  retn
```

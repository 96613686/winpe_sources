# ParseUncPathEx

- ea: `0x180009f8c`
- end: `0x18000a0ea`
- name: `ParseUncPathEx`
- size: `350`
- prototype: `__int64(wchar_t *String1, _DWORD *, LPVOID *, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a0f0`

## callees

- `0x1800029a5`
- `0x180009528`
- `0x180009f8c`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180009fdd`
- `msvcrt!_wcsnicmp` at `0x18000a010`
- `msvcrt!_wcsnicmp` at `0x180009fdd`
- `msvcrt!_wcsnicmp` at `0x18000a010`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a0b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a0b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a0c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a0c1`

## pseudocode

```c
__int64 ParseUncPathEx(wchar_t *String1, _DWORD *a2, LPVOID *a3, ...)
{
  __int64 v7; // rbx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rax
  BOOL v10; // ecx
  wchar_t *v11; // rax
  int v12; // ebx
  void *v13; // rsi
  wchar_t *v14; // rax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+78h] [rbp+20h] BYREF
  va_list lpMema; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(lpMema, a3);
  lpMem = va_arg(va1, LPVOID);
  if ( !String1 )
    return 2147942487LL;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( String1[v8] );
  if ( v8 < 2 || _wcsnicmp(String1, L"\\\\", 2u) )
  {
    v12 = 0;
    if ( a2 )
      *a2 = 0;
    if ( a3 )
      *a3 = 0;
    return (unsigned int)v12;
  }
  v9 = -1;
  do
    ++v9;
  while ( String1[v9] );
  v10 = v9 >= 8 && _wcsnicmp(String1, L"\\\\?\\UNC\\", 8u) == 0;
  v11 = wcschr_0((wchar_t *)((char *)String1 + (v10 ? 16LL : 4LL)), 0x5Cu);
  if ( v11 )
  {
    v13 = 0;
    lpMem = 0;
    do
      ++v7;
    while ( String1[v7] );
    v14 = wcschr_0(v11 + 1, 0x5Cu);
    if ( v14 )
      v7 = v14 - String1;
    if ( a3 )
    {
      v12 = StrSubstring(String1, 0, v7, (LPVOID *)lpMema);
      if ( v12 < 0 )
      {
        v13 = lpMem;
LABEL_25:
        if ( v13 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v13);
        }
        return (unsigned int)v12;
      }
      *a3 = lpMem;
    }
    else
    {
      v12 = 0;
    }
    if ( a2 )
      *a2 = 1;
    goto LABEL_25;
  }
  return (unsigned int)-2147024883;
}

```

## disassembly

```asm
0x180009f8c  mov     [rsp+lpMem], r9
0x180009f91  push    rbx
0x180009f92  push    rbp
0x180009f93  push    rsi
0x180009f94  push    rdi
0x180009f95  push    r14
0x180009f97  push    r15
0x180009f99  sub     rsp, 28h
0x180009f9d  xor     ebp, ebp
0x180009f9f  mov     r15, r8
0x180009fa2  mov     r14, rdx
0x180009fa5  mov     rdi, rcx
0x180009fa8  test    rcx, rcx
0x180009fab  jnz     short loc_180009FB7
0x180009fad  mov     eax, 80070057h
0x180009fb2  jmp     loc_18000A0DD
0x180009fb7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009fbb  mov     rax, rbx
0x180009fbe  inc     rax
0x180009fc1  cmp     [rcx+rax*2], bp
0x180009fc5  jnz     short loc_180009FBE
0x180009fc7  mov     r8d, 2; MaxCount
0x180009fcd  cmp     rax, r8
0x180009fd0  jb      loc_18000A0C9
0x180009fd6  lea     rdx, asc_180019568; "\\\\"
0x180009fdd  call    cs:__imp__wcsnicmp
0x180009fe3  test    eax, eax
0x180009fe5  jnz     loc_18000A0C9
0x180009feb  mov     rax, rbx
0x180009fee  inc     rax
0x180009ff1  cmp     [rdi+rax*2], bp
0x180009ff5  jnz     short loc_180009FEE
0x180009ff7  mov     r8d, 8; MaxCount
0x180009ffd  cmp     rax, r8
0x18000a000  jnb     short loc_18000A006
0x18000a002  mov     ecx, ebp
0x18000a004  jmp     short loc_18000A01D
0x18000a006  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x18000a00d  mov     rcx, rdi; String1
0x18000a010  call    cs:__imp__wcsnicmp
0x18000a016  test    eax, eax
0x18000a018  mov     ecx, ebp
0x18000a01a  setz    cl
0x18000a01d  neg     ecx
0x18000a01f  mov     edx, 5Ch ; '\'; Ch
0x18000a024  sbb     rcx, rcx
0x18000a027  and     ecx, 0Ch
0x18000a02a  add     rcx, 4
0x18000a02e  add     rcx, rdi; Str
0x18000a031  call    wcschr_0
0x18000a036  test    rax, rax
0x18000a039  jnz     short loc_18000A045
0x18000a03b  mov     ebx, 8007000Dh
0x18000a040  jmp     loc_18000A0DB
0x18000a045  mov     rsi, rbp
0x18000a048  mov     [rsp+58h+lpMem], rbp
0x18000a04d  inc     rbx
0x18000a050  cmp     [rdi+rbx*2], bp
0x18000a054  jnz     short loc_18000A04D
0x18000a056  mov     edx, 5Ch ; '\'; Ch
0x18000a05b  lea     rcx, [rax+2]; Str
0x18000a05f  call    wcschr_0
0x18000a064  test    rax, rax
0x18000a067  jz      short loc_18000A072
0x18000a069  mov     rbx, rax
0x18000a06c  sub     rbx, rdi
0x18000a06f  sar     rbx, 1
0x18000a072  test    r15, r15
0x18000a075  jz      short loc_18000A0A0
0x18000a077  lea     r9, [rsp+58h+lpMem]
0x18000a07c  mov     r8, rbx
0x18000a07f  xor     edx, edx
0x18000a081  mov     rcx, rdi
0x18000a084  call    StrSubstring
0x18000a089  mov     ebx, eax
0x18000a08b  test    eax, eax
0x18000a08d  js      short loc_18000A099
0x18000a08f  mov     rax, [rsp+58h+lpMem]
0x18000a094  mov     [r15], rax
0x18000a097  jmp     short loc_18000A0A2
0x18000a099  mov     rsi, [rsp+58h+lpMem]
0x18000a09e  jmp     short loc_18000A0AE
0x18000a0a0  mov     ebx, ebp
0x18000a0a2  test    r14, r14
0x18000a0a5  jz      short loc_18000A0AE
0x18000a0a7  mov     dword ptr [r14], 1
0x18000a0ae  test    rsi, rsi
0x18000a0b1  jz      short loc_18000A0DB
0x18000a0b3  call    cs:__imp_GetProcessHeap
0x18000a0b9  mov     r8, rsi; lpMem
0x18000a0bc  xor     edx, edx; dwFlags
0x18000a0be  mov     rcx, rax; hHeap
0x18000a0c1  call    cs:__imp_HeapFree
0x18000a0c7  jmp     short loc_18000A0DB
0x18000a0c9  mov     ebx, ebp
0x18000a0cb  test    r14, r14
0x18000a0ce  jz      short loc_18000A0D3
0x18000a0d0  mov     [r14], ebp
0x18000a0d3  test    r15, r15
0x18000a0d6  jz      short loc_18000A0DB
0x18000a0d8  mov     [r15], rbp
0x18000a0db  mov     eax, ebx
0x18000a0dd  add     rsp, 28h
0x18000a0e1  pop     r15
0x18000a0e3  pop     r14
0x18000a0e5  pop     rdi
0x18000a0e6  pop     rsi
0x18000a0e7  pop     rbp
0x18000a0e8  pop     rbx
0x18000a0e9  retn
```

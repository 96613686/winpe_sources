# ?get_Name@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAPEAG@Z

- ea: `0x180030500`
- end: `0x1800305b8`
- name: `?get_Name@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAPEAG@Z`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180030500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030583`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003059b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030583`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003059b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003053e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003053e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180030558`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180030558`
- `OLEAUT32!__imp_SysAllocString` at `0x180030567`
- `OLEAUT32!__imp_SysAllocString` at `0x180030567`

## pseudocode

```c
__int64 __fastcall _get_Name__QIRegisteredTask__RegisteredTaskImpl__UEAAJPEAPEAG_Z(__int64 a1, BSTR *a2)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  const WCHAR *v7; // rcx
  const OLECHAR *FileNameW; // rax
  BSTR v9; // rax

  if ( !a2 )
    return 2147500035LL;
  v5 = (a1 + 16) & -(__int64)(a1 != 0);
  if ( v5 )
  {
    v6 = v5 + 8;
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  }
  else
  {
    v6 = 8;
  }
  v7 = (const WCHAR *)(a1 + 80);
  if ( *(_QWORD *)(a1 + 104) >= 8u )
    v7 = *(const WCHAR **)v7;
  FileNameW = PathFindFileNameW(v7);
  v9 = SysAllocString(FileNameW);
  *a2 = v9;
  if ( v9 )
  {
    if ( v5 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v6);
    return 0;
  }
  else
  {
    if ( v5 )
      LeaveCriticalSection((LPCRITICAL_SECTION)v6);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180030500  push    rbx
0x180030502  push    rsi
0x180030503  push    rdi
0x180030504  push    r14
0x180030506  sub     rsp, 28h
0x18003050a  mov     r14, rdx
0x18003050d  mov     rsi, rcx
0x180030510  test    rdx, rdx
0x180030513  jnz     short loc_180030525
0x180030515  mov     eax, 80004003h
0x18003051a  add     rsp, 28h
0x18003051e  pop     r14
0x180030520  pop     rdi
0x180030521  pop     rsi
0x180030522  pop     rbx
0x180030523  retn
0x180030525  add     rcx, 10h
0x180030529  mov     rax, rsi
0x18003052c  neg     rax
0x18003052f  sbb     rbx, rbx
0x180030532  and     rbx, rcx
0x180030535  jz      short loc_1800305B1
0x180030537  lea     rdi, [rbx+8]
0x18003053b  mov     rcx, rdi; lpCriticalSection
0x18003053e  call    cs:__imp_EnterCriticalSection
0x180030545  nop     dword ptr [rax+rax+00h]
0x18003054a  lea     rcx, [rsi+50h]
0x18003054e  cmp     qword ptr [rcx+18h], 8
0x180030553  jb      short loc_180030558
0x180030555  mov     rcx, [rcx]; pszPath
0x180030558  call    cs:__imp_PathFindFileNameW
0x18003055f  nop     dword ptr [rax+rax+00h]
0x180030564  mov     rcx, rax; psz
0x180030567  call    cs:__imp_SysAllocString
0x18003056e  nop     dword ptr [rax+rax+00h]
0x180030573  mov     [r14], rax
0x180030576  test    rax, rax
0x180030579  jz      short loc_180030593
0x18003057b  test    rbx, rbx
0x18003057e  jz      short loc_18003058F
0x180030580  mov     rcx, rdi; lpCriticalSection
0x180030583  call    cs:__imp_LeaveCriticalSection
0x18003058a  nop     dword ptr [rax+rax+00h]
0x18003058f  xor     eax, eax
0x180030591  jmp     short loc_18003051A
0x180030593  test    rbx, rbx
0x180030596  jz      short loc_1800305A7
0x180030598  mov     rcx, rdi; lpCriticalSection
0x18003059b  call    cs:__imp_LeaveCriticalSection
0x1800305a2  nop     dword ptr [rax+rax+00h]
0x1800305a7  mov     eax, 8007000Eh
0x1800305ac  jmp     loc_18003051A
0x1800305b1  mov     edi, 8
0x1800305b6  jmp     short loc_18003054A
```

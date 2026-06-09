# CTimeRunList::MakeSysTimeArray(_SYSTEMTIME * *,ushort *)

- ea: `0x18002d48c`
- end: `0x18002d517`
- name: `?MakeSysTimeArray@CTimeRunList@@QEAAJPEAPEAU_SYSTEMTIME@@PEAG@Z`
- size: `139`
- prototype: `__int64 __fastcall(CTimeRunList *__hidden this, struct _SYSTEMTIME **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026bc0`

## callees

- `0x18002d48c`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002d4ef`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002d4ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d4af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d4af`

## pseudocode

```c
__int64 __fastcall CTimeRunList::MakeSysTimeArray(CTimeRunList *this, struct _SYSTEMTIME **a2, unsigned __int16 *a3)
{
  unsigned __int16 v3; // si
  SIZE_T v5; // rcx
  struct _SYSTEMTIME *v8; // rax
  unsigned __int16 v10; // ax
  __int64 v11; // rbx

  v3 = *a3;
  v5 = 16LL * *a3;
  *a3 = 0;
  v8 = (struct _SYSTEMTIME *)CoTaskMemAlloc(v5);
  *a2 = v8;
  if ( !v8 )
    return 2147942414LL;
  v10 = *a3;
  if ( *a3 < v3 )
  {
    v11 = *((_QWORD *)this + 1);
    do
    {
      if ( !*(_DWORD *)(v11 + 24) && !*(_DWORD *)(v11 + 28) )
        break;
      FileTimeToSystemTime((const FILETIME *)(v11 + 24), &(*a2)[v10]);
      v10 = ++*a3;
      v11 = *(_QWORD *)(v11 + 8);
    }
    while ( *a3 < v3 );
  }
  return 0;
}

```

## disassembly

```asm
0x18002d48c  push    rbx
0x18002d48e  push    rsi
0x18002d48f  push    rdi
0x18002d490  push    r14
0x18002d492  sub     rsp, 28h
0x18002d496  movzx   esi, word ptr [r8]
0x18002d49a  mov     rbx, rcx
0x18002d49d  xor     eax, eax
0x18002d49f  mov     ecx, esi
0x18002d4a1  shl     rcx, 4; cb
0x18002d4a5  mov     rdi, r8
0x18002d4a8  mov     r14, rdx
0x18002d4ab  mov     [r8], ax
0x18002d4af  call    cs:__imp_CoTaskMemAlloc
0x18002d4b6  nop     dword ptr [rax+rax+00h]
0x18002d4bb  mov     [r14], rax
0x18002d4be  test    rax, rax
0x18002d4c1  jnz     short loc_18002D4CA
0x18002d4c3  mov     eax, 8007000Eh
0x18002d4c8  jmp     short loc_18002D50C
0x18002d4ca  movzx   eax, word ptr [rdi]
0x18002d4cd  cmp     ax, si
0x18002d4d0  jnb     short loc_18002D50A
0x18002d4d2  mov     rbx, [rbx+8]
0x18002d4d6  lea     rcx, [rbx+18h]; lpFileTime
0x18002d4da  cmp     dword ptr [rcx], 0
0x18002d4dd  jnz     short loc_18002D4E5
0x18002d4df  cmp     dword ptr [rbx+1Ch], 0
0x18002d4e3  jz      short loc_18002D50A
0x18002d4e5  movzx   edx, ax
0x18002d4e8  shl     rdx, 4
0x18002d4ec  add     rdx, [r14]; lpSystemTime
0x18002d4ef  call    cs:__imp_FileTimeToSystemTime
0x18002d4f6  nop     dword ptr [rax+rax+00h]
0x18002d4fb  inc     word ptr [rdi]
0x18002d4fe  movzx   eax, word ptr [rdi]
0x18002d501  mov     rbx, [rbx+8]
0x18002d505  cmp     ax, si
0x18002d508  jb      short loc_18002D4D6
0x18002d50a  xor     eax, eax
0x18002d50c  add     rsp, 28h
0x18002d510  pop     r14
0x18002d512  pop     rdi
0x18002d513  pop     rsi
0x18002d514  pop     rbx
0x18002d515  retn
```

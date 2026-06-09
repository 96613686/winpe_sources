# DwQueryHeader(_EXTENSION_CONTROL_BLOCK *,char const *,char * *)

- ea: `0x1800025e8`
- end: `0x18000269d`
- name: `?DwQueryHeader@@YAKPEAU_EXTENSION_CONTROL_BLOCK@@PEBDPEAPEAD@Z`
- size: `181`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *, const char *, char **)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002110`
- `0x180006d7c`
- `0x180006f64`
- `0x1800071bc`
- `0x180007310`
- `0x180007734`
- `0x180007d1c`

## callees

- `0x1800025e8`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002674`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002674`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000263c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000263c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000262b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000262b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002669`

## pseudocode

```c
__int64 __fastcall DwQueryHeader(struct _EXTENSION_CONTROL_BLOCK *a1, const char *a2, char **a3)
{
  HCONN ConnID; // rcx
  DWORD LastError; // ebx
  char *v8; // rax
  char *v9; // rdi
  size_t Size; // [rsp+50h] [rbp+8h] BYREF

  LODWORD(Size) = 0;
  ConnID = a1->ConnID;
  LastError = 0;
  *a3 = 0;
  if ( !((unsigned int (__fastcall *)(HCONN, const char *, _QWORD, size_t *))a1->GetServerVariable)(
          ConnID,
          a2,
          0,
          &Size) )
  {
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v8 = (char *)malloc((unsigned int)Size);
      v9 = v8;
      if ( v8 )
      {
        if ( ((unsigned int (__fastcall *)(HCONN, const char *, char *, size_t *))a1->GetServerVariable)(
               a1->ConnID,
               a2,
               v8,
               &Size) )
        {
          *a3 = v9;
          return 0;
        }
        else
        {
          LastError = GetLastError();
          free(v9);
        }
      }
      else
      {
        return 14;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800025e8  mov     rax, rsp
0x1800025eb  mov     [rax+10h], rbx
0x1800025ef  mov     [rax+18h], rbp
0x1800025f3  push    rsi
0x1800025f4  push    rdi
0x1800025f5  push    r14
0x1800025f7  sub     rsp, 30h
0x1800025fb  mov     rsi, rcx
0x1800025fe  mov     dword ptr [rax+8], 0
0x180002605  mov     rcx, [rcx+8]
0x180002609  lea     r9, [rax+8]
0x18000260d  mov     r14, r8
0x180002610  xor     ebx, ebx
0x180002612  mov     [r8], rbx
0x180002615  mov     rbp, rdx
0x180002618  mov     rax, [rsi+0A0h]
0x18000261f  xor     r8d, r8d
0x180002622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002627  test    eax, eax
0x180002629  jnz     short loc_180002688
0x18000262b  call    cs:__imp_GetLastError
0x180002631  mov     ebx, eax
0x180002633  cmp     eax, 7Ah ; 'z'
0x180002636  jnz     short loc_180002688
0x180002638  mov     ecx, dword ptr [rsp+48h+Size]; Size
0x18000263c  call    cs:__imp_malloc
0x180002642  mov     rdi, rax
0x180002645  test    rax, rax
0x180002648  jz      short loc_180002683
0x18000264a  mov     rcx, [rsi+8]
0x18000264e  lea     r9, [rsp+48h+Size]
0x180002653  mov     r8, rax
0x180002656  mov     rdx, rbp
0x180002659  mov     rax, [rsi+0A0h]
0x180002660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002665  test    eax, eax
0x180002667  jnz     short loc_18000267C
0x180002669  call    cs:__imp_GetLastError
0x18000266f  mov     rcx, rdi; Block
0x180002672  mov     ebx, eax
0x180002674  call    cs:__imp_free
0x18000267a  jmp     short loc_180002688
0x18000267c  mov     [r14], rdi
0x18000267f  xor     ebx, ebx
0x180002681  jmp     short loc_180002688
0x180002683  mov     ebx, 0Eh
0x180002688  mov     rbp, [rsp+48h+arg_10]
0x18000268d  mov     eax, ebx
0x18000268f  mov     rbx, [rsp+48h+arg_8]
0x180002694  add     rsp, 30h
0x180002698  pop     r14
0x18000269a  pop     rdi
0x18000269b  pop     rsi
0x18000269c  retn
```

# DavFinalizeFileAttributesList

- ea: `0x180028440`
- end: `0x18002857d`
- name: `DavFinalizeFileAttributesList`
- size: `317`
- prototype: `HLOCAL __fastcall(char *hMem, int)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1800049bc`
- `0x1800091e0`
- `0x18000a770`
- `0x18000ca80`
- `0x18000d9e4`
- `0x18001507c`
- `0x18001a5a0`
- `0x18001ad0c`
- `0x18001c6e8`
- `0x18001dcb4`
- `0x1800206bc`
- `0x1800229b0`
- `0x180025330`

## callees

- `0x180028440`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18002848b`
- `KERNEL32!LocalFree` at `0x1800284a2`
- `KERNEL32!LocalFree` at `0x1800284bc`
- `KERNEL32!LocalFree` at `0x1800284d9`
- `KERNEL32!LocalFree` at `0x1800284ed`
- `KERNEL32!LocalFree` at `0x180028505`
- `KERNEL32!LocalFree` at `0x18002851c`
- `KERNEL32!LocalFree` at `0x180028536`
- `KERNEL32!LocalFree` at `0x180028553`
- `KERNEL32!LocalFree` at `0x18002856c`
- `KERNEL32!LocalFree` at `0x18002848b`
- `KERNEL32!LocalFree` at `0x1800284a2`
- `KERNEL32!LocalFree` at `0x1800284bc`
- `KERNEL32!LocalFree` at `0x1800284d9`
- `KERNEL32!LocalFree` at `0x1800284ed`
- `KERNEL32!LocalFree` at `0x180028505`
- `KERNEL32!LocalFree` at `0x18002851c`
- `KERNEL32!LocalFree` at `0x180028536`
- `KERNEL32!LocalFree` at `0x180028553`
- `KERNEL32!LocalFree` at `0x18002856c`

## pseudocode

```c
HLOCAL __fastcall DavFinalizeFileAttributesList(char *hMem, int a2)
{
  char *v2; // r14
  char *v4; // rsi
  char *v6; // rdi
  char **v7; // rax
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  HLOCAL result; // rax
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx

  if ( hMem )
  {
    v2 = hMem + 64;
    v4 = (char *)*((_QWORD *)hMem + 8);
    while ( v4 && v4 != v2 )
    {
      v6 = v4 - 64;
      v7 = (char **)*((_QWORD *)v4 + 1);
      v4 = *(char **)v4;
      *v7 = v4;
      *((_QWORD *)v4 + 1) = v7;
      v8 = (void *)*((_QWORD *)v6 + 13);
      if ( v8 )
      {
        LocalFree(v8);
        *((_QWORD *)v6 + 13) = 0;
      }
      v9 = (void *)*((_QWORD *)v6 + 12);
      if ( v9 )
      {
        LocalFree(v9);
        *((_QWORD *)v6 + 12) = 0;
      }
      v10 = (void *)*((_QWORD *)v6 + 19);
      if ( v10 )
      {
        LocalFree(v10);
        *((_QWORD *)v6 + 19) = 0;
      }
      v11 = (void *)*((_QWORD *)v6 + 18);
      if ( v11 )
      {
        LocalFree(v11);
        *((_QWORD *)v6 + 18) = 0;
      }
      result = LocalFree(v6);
    }
    v13 = (void *)*((_QWORD *)hMem + 13);
    if ( v13 )
    {
      result = LocalFree(v13);
      *((_QWORD *)hMem + 13) = 0;
    }
    v14 = (void *)*((_QWORD *)hMem + 12);
    if ( v14 )
    {
      result = LocalFree(v14);
      *((_QWORD *)hMem + 12) = 0;
    }
    v15 = (void *)*((_QWORD *)hMem + 19);
    if ( v15 )
    {
      result = LocalFree(v15);
      *((_QWORD *)hMem + 19) = 0;
    }
    v16 = (void *)*((_QWORD *)hMem + 18);
    if ( v16 )
    {
      result = LocalFree(v16);
      *((_QWORD *)hMem + 18) = 0;
    }
    if ( a2 == 1 )
      return LocalFree(hMem);
  }
  return result;
}

```

## disassembly

```asm
0x180028440  test    rcx, rcx
0x180028443  jz      locret_18002857C
0x180028449  push    rbx
0x18002844a  push    rbp
0x18002844b  push    rsi
0x18002844c  push    rdi
0x18002844d  push    r14
0x18002844f  sub     rsp, 20h
0x180028453  lea     r14, [rcx+40h]
0x180028457  mov     ebp, edx
0x180028459  mov     rsi, [r14]
0x18002845c  mov     rbx, rcx
0x18002845f  jmp     loc_1800284F3
0x180028464  cmp     rsi, r14
0x180028467  jz      loc_1800284FC
0x18002846d  mov     rcx, [rsi]
0x180028470  lea     rdi, [rsi-40h]
0x180028474  mov     rax, [rsi+8]
0x180028478  mov     rsi, rcx
0x18002847b  mov     [rax], rcx
0x18002847e  mov     [rcx+8], rax
0x180028482  mov     rcx, [rdi+68h]; hMem
0x180028486  test    rcx, rcx
0x180028489  jz      short loc_180028499
0x18002848b  call    cs:__imp_LocalFree
0x180028491  mov     qword ptr [rdi+68h], 0
0x180028499  mov     rcx, [rdi+60h]; hMem
0x18002849d  test    rcx, rcx
0x1800284a0  jz      short loc_1800284B0
0x1800284a2  call    cs:__imp_LocalFree
0x1800284a8  mov     qword ptr [rdi+60h], 0
0x1800284b0  mov     rcx, [rdi+98h]; hMem
0x1800284b7  test    rcx, rcx
0x1800284ba  jz      short loc_1800284CD
0x1800284bc  call    cs:__imp_LocalFree
0x1800284c2  mov     qword ptr [rdi+98h], 0
0x1800284cd  mov     rcx, [rdi+90h]; hMem
0x1800284d4  test    rcx, rcx
0x1800284d7  jz      short loc_1800284EA
0x1800284d9  call    cs:__imp_LocalFree
0x1800284df  mov     qword ptr [rdi+90h], 0
0x1800284ea  mov     rcx, rdi; hMem
0x1800284ed  call    cs:__imp_LocalFree
0x1800284f3  test    rsi, rsi
0x1800284f6  jnz     loc_180028464
0x1800284fc  mov     rcx, [rbx+68h]; hMem
0x180028500  test    rcx, rcx
0x180028503  jz      short loc_180028513
0x180028505  call    cs:__imp_LocalFree
0x18002850b  mov     qword ptr [rbx+68h], 0
0x180028513  mov     rcx, [rbx+60h]; hMem
0x180028517  test    rcx, rcx
0x18002851a  jz      short loc_18002852A
0x18002851c  call    cs:__imp_LocalFree
0x180028522  mov     qword ptr [rbx+60h], 0
0x18002852a  mov     rcx, [rbx+98h]; hMem
0x180028531  test    rcx, rcx
0x180028534  jz      short loc_180028547
0x180028536  call    cs:__imp_LocalFree
0x18002853c  mov     qword ptr [rbx+98h], 0
0x180028547  mov     rcx, [rbx+90h]; hMem
0x18002854e  test    rcx, rcx
0x180028551  jz      short loc_180028564
0x180028553  call    cs:__imp_LocalFree
0x180028559  mov     qword ptr [rbx+90h], 0
0x180028564  cmp     ebp, 1
0x180028567  jnz     short loc_180028572
0x180028569  mov     rcx, rbx; hMem
0x18002856c  call    cs:__imp_LocalFree
0x180028572  add     rsp, 20h
0x180028576  pop     r14
0x180028578  pop     rdi
0x180028579  pop     rsi
0x18002857a  pop     rbp
0x18002857b  pop     rbx
0x18002857c  retn
```

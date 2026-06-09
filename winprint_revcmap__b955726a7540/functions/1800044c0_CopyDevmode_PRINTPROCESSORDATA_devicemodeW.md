# CopyDevmode(_PRINTPROCESSORDATA *,_devicemodeW * *)

- ea: `0x1800044c0`
- end: `0x1800045c0`
- name: `?CopyDevmode@@YAHPEAU_PRINTPROCESSORDATA@@PEAPEAU_devicemodeW@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct _PRINTPROCESSORDATA *, struct _devicemodeW **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002400`

## callees

- `0x1800044c0`
- `0x1800077b5`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800044f8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000455a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800044f8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000455a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000459c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000459c`
- `WINSPOOL!ClosePrinter` at `0x1800045af`
- `WINSPOOL!ClosePrinter` at `0x1800045af`
- `WINSPOOL!OpenPrinterW` at `0x180004527`
- `WINSPOOL!OpenPrinterW` at `0x180004527`
- `WINSPOOL!DocumentPropertiesW` at `0x180004548`
- `WINSPOOL!DocumentPropertiesW` at `0x180004583`
- `WINSPOOL!DocumentPropertiesW` at `0x180004548`
- `WINSPOOL!DocumentPropertiesW` at `0x180004583`

## pseudocode

```c
__int64 __fastcall CopyDevmode(struct _PRINTPROCESSORDATA *a1, HLOCAL *a2)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  SIZE_T v6; // rbp
  struct _devicemodeW *v7; // rax
  LONG v8; // eax
  struct _devicemodeW *v9; // rax
  HANDLE phPrinter; // [rsp+60h] [rbp+8h] BYREF

  *a2 = 0;
  v4 = *((_QWORD *)a1 + 14);
  v5 = 0;
  phPrinter = 0;
  if ( v4 )
  {
    v6 = *(unsigned __int16 *)(v4 + 68) + (unsigned __int64)*(unsigned __int16 *)(v4 + 70);
    v7 = (struct _devicemodeW *)LocalAlloc(0x40u, v6);
    *a2 = v7;
    if ( !v7 )
      goto LABEL_11;
    memcpy_0(v7, *((const void **)a1 + 14), v6);
LABEL_8:
    v5 = 1;
    goto LABEL_11;
  }
  if ( !OpenPrinterW(*((LPWSTR *)a1 + 6), &phPrinter, 0) )
    goto LABEL_11;
  v8 = DocumentPropertiesW(0, phPrinter, *((LPWSTR *)a1 + 6), 0, 0, 0);
  if ( v8 > 0 )
  {
    v9 = (struct _devicemodeW *)LocalAlloc(0x40u, v8);
    *a2 = v9;
    if ( v9 )
    {
      if ( DocumentPropertiesW(0, phPrinter, *((LPWSTR *)a1 + 6), v9, 0, 2u) >= 0 )
        goto LABEL_8;
    }
  }
  if ( *a2 )
  {
    LocalFree(*a2);
    *a2 = 0;
  }
LABEL_11:
  if ( phPrinter )
    ClosePrinter(phPrinter);
  return v5;
}

```

## disassembly

```asm
0x1800044c0  push    rbx
0x1800044c2  push    rbp
0x1800044c3  push    rsi
0x1800044c4  push    rdi
0x1800044c5  sub     rsp, 38h
0x1800044c9  xor     ebp, ebp
0x1800044cb  mov     rdi, rdx
0x1800044ce  mov     [rdx], rbp
0x1800044d1  mov     rsi, rcx
0x1800044d4  mov     rax, [rcx+70h]
0x1800044d8  mov     ebx, ebp
0x1800044da  mov     [rsp+58h+phPrinter], rbp
0x1800044df  test    rax, rax
0x1800044e2  jz      short loc_18000451B
0x1800044e4  movzx   ebp, word ptr [rax+46h]
0x1800044e8  mov     ecx, 40h ; '@'; uFlags
0x1800044ed  movzx   r8d, word ptr [rax+44h]
0x1800044f2  add     rbp, r8
0x1800044f5  mov     rdx, rbp; uBytes
0x1800044f8  call    cs:__imp_LocalAlloc
0x1800044fe  mov     [rdi], rax
0x180004501  test    rax, rax
0x180004504  jz      loc_1800045A5
0x18000450a  mov     rdx, [rsi+70h]; Src
0x18000450e  mov     r8, rbp; Size
0x180004511  mov     rcx, rax; void *
0x180004514  call    memcpy_0
0x180004519  jmp     short loc_18000458D
0x18000451b  mov     rcx, [rcx+30h]; pPrinterName
0x18000451f  lea     rdx, [rsp+58h+phPrinter]; phPrinter
0x180004524  xor     r8d, r8d; pDefault
0x180004527  call    cs:__imp_OpenPrinterW
0x18000452d  test    eax, eax
0x18000452f  jz      short loc_1800045A5
0x180004531  mov     r8, [rsi+30h]; pDeviceName
0x180004535  xor     r9d, r9d; pDevModeOutput
0x180004538  mov     rdx, [rsp+58h+phPrinter]; hPrinter
0x18000453d  xor     ecx, ecx; hWnd
0x18000453f  mov     [rsp+58h+fMode], ebp; fMode
0x180004543  mov     [rsp+58h+pDevModeInput], rbp; pDevModeInput
0x180004548  call    cs:__imp_DocumentPropertiesW
0x18000454e  test    eax, eax
0x180004550  jle     short loc_180004594
0x180004552  movsxd  rdx, eax; uBytes
0x180004555  mov     ecx, 40h ; '@'; uFlags
0x18000455a  call    cs:__imp_LocalAlloc
0x180004560  mov     [rdi], rax
0x180004563  test    rax, rax
0x180004566  jz      short loc_180004594
0x180004568  mov     r8, [rsi+30h]; pDeviceName
0x18000456c  mov     r9, rax; pDevModeOutput
0x18000456f  mov     rdx, [rsp+58h+phPrinter]; hPrinter
0x180004574  xor     ecx, ecx; hWnd
0x180004576  mov     [rsp+58h+fMode], 2; fMode
0x18000457e  mov     [rsp+58h+pDevModeInput], rbp; pDevModeInput
0x180004583  call    cs:__imp_DocumentPropertiesW
0x180004589  test    eax, eax
0x18000458b  js      short loc_180004594
0x18000458d  mov     ebx, 1
0x180004592  jmp     short loc_1800045A5
0x180004594  mov     rcx, [rdi]; hMem
0x180004597  test    rcx, rcx
0x18000459a  jz      short loc_1800045A5
0x18000459c  call    cs:__imp_LocalFree
0x1800045a2  mov     [rdi], rbp
0x1800045a5  mov     rcx, [rsp+58h+phPrinter]; hPrinter
0x1800045aa  test    rcx, rcx
0x1800045ad  jz      short loc_1800045B5
0x1800045af  call    cs:__imp_ClosePrinter
0x1800045b5  mov     eax, ebx
0x1800045b7  add     rsp, 38h
0x1800045bb  pop     rdi
0x1800045bc  pop     rsi
0x1800045bd  pop     rbp
0x1800045be  pop     rbx
0x1800045bf  retn
```

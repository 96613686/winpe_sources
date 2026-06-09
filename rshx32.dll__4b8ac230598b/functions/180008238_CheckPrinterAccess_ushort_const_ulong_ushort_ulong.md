# CheckPrinterAccess(ushort const *,ulong *,ushort *,ulong)

- ea: `0x180008238`
- end: `0x180008386`
- name: `?CheckPrinterAccess@@YAJPEBGPEAKPEAGK@Z`
- size: `334`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a440`

## callees

- `0x180005610`
- `0x180008238`
- `0x18000847c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008358`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008358`
- `WINSPOOL!ClosePrinter` at `0x1800082cd`
- `WINSPOOL!ClosePrinter` at `0x180008362`
- `WINSPOOL!ClosePrinter` at `0x1800082cd`
- `WINSPOOL!ClosePrinter` at `0x180008362`
- `WINSPOOL!OpenPrinterW` at `0x1800082bd`
- `WINSPOOL!OpenPrinterW` at `0x18000830d`
- `WINSPOOL!OpenPrinterW` at `0x1800082bd`
- `WINSPOOL!OpenPrinterW` at `0x18000830d`

## pseudocode

```c
__int64 __fastcall CheckPrinterAccess(LPWSTR pPrinterName, unsigned int *a2, unsigned __int16 *a3)
{
  __int64 v7; // rdi
  int v8; // ebx
  signed int LastError; // eax
  unsigned int v10; // ebx
  const unsigned __int16 **v11; // r11
  HLOCAL hMem; // [rsp+20h] [rbp-48h] BYREF
  _DWORD v13[6]; // [rsp+28h] [rbp-40h]
  _PRINTER_DEFAULTSW pDefault; // [rsp+40h] [rbp-28h] BYREF
  HANDLE phPrinter; // [rsp+A8h] [rbp+40h] BYREF

  v13[0] = 17694720;
  v13[1] = 0x20000;
  v13[2] = 0x40000;
  v13[3] = 0x80000;
  v13[4] = 0x1000000;
  phPrinter = 0;
  memset(&pDefault, 0, sizeof(pDefault));
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v7 = 0;
  while ( 1 )
  {
    v8 = v13[v7];
    if ( (v8 & *a2) != v8 )
      break;
LABEL_9:
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= 5 )
    {
      v10 = 0;
      if ( a3 )
      {
        pDefault.DesiredAccess = 131080;
        if ( OpenPrinterW(pPrinterName, &phPrinter, &pDefault) )
        {
          hMem = 0;
          if ( (unsigned int)GetPrinterAlloc(phPrinter, 2u, (unsigned __int8 **)&hMem) )
          {
            v11 = (const unsigned __int16 **)hMem;
            *a3 = 0;
            if ( v11 )
            {
              if ( *v11 )
                v10 = StringCchCopyW(a3, 0x104u, *v11);
            }
            LocalFree(v11);
          }
          ClosePrinter(phPrinter);
        }
      }
      return v10;
    }
  }
  pDefault.DesiredAccess = v13[v7];
  if ( OpenPrinterW(pPrinterName, &phPrinter, &pDefault) )
  {
    *a2 |= v8;
    ClosePrinter(phPrinter);
    goto LABEL_9;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError == 5 || LastError == 1314 )
    goto LABEL_9;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v10;
}

```

## disassembly

```asm
0x180008238  push    rbp
0x18000823a  push    rbx
0x18000823b  push    rsi
0x18000823c  push    rdi
0x18000823d  push    r14
0x18000823f  push    r15
0x180008241  mov     rbp, rsp
0x180008244  sub     rsp, 68h
0x180008248  mov     qword ptr [rbp+pDefault.DesiredAccess], 0
0x180008250  xorps   xmm0, xmm0
0x180008253  mov     [rbp+var_40], 10E0000h
0x18000825a  mov     r14, r8
0x18000825d  mov     [rbp+var_3C], 20000h
0x180008264  mov     rsi, rdx
0x180008267  mov     [rbp+var_38], 40000h
0x18000826e  mov     r15, rcx
0x180008271  mov     [rbp+var_34], 80000h
0x180008278  mov     [rbp+var_30], 1000000h
0x18000827f  mov     [rbp+phPrinter], 0
0x180008287  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x18000828c  test    rdx, rdx
0x18000828f  jnz     short loc_18000829B
0x180008291  mov     eax, 80004003h
0x180008296  jmp     loc_18000836A
0x18000829b  mov     dword ptr [rdx], 0
0x1800082a1  xor     edi, edi
0x1800082a3  mov     ebx, [rbp+rdi*4+var_40]
0x1800082a7  mov     eax, [rsi]
0x1800082a9  and     eax, ebx
0x1800082ab  cmp     eax, ebx
0x1800082ad  jz      short loc_1800082ED
0x1800082af  lea     r8, [rbp+pDefault]; pDefault
0x1800082b3  mov     [rbp+pDefault.DesiredAccess], ebx
0x1800082b6  lea     rdx, [rbp+phPrinter]; phPrinter
0x1800082ba  mov     rcx, r15; pPrinterName
0x1800082bd  call    cs:__imp_OpenPrinterW
0x1800082c3  test    eax, eax
0x1800082c5  jz      short loc_1800082D5
0x1800082c7  or      [rsi], ebx
0x1800082c9  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800082cd  call    cs:__imp_ClosePrinter
0x1800082d3  jmp     short loc_1800082ED
0x1800082d5  call    cs:__imp_GetLastError
0x1800082db  mov     ebx, eax
0x1800082dd  cmp     eax, 5
0x1800082e0  jz      short loc_1800082ED
0x1800082e2  cmp     eax, 522h
0x1800082e7  jnz     loc_180008377
0x1800082ed  inc     edi
0x1800082ef  cmp     edi, 5
0x1800082f2  jb      short loc_1800082A3
0x1800082f4  xor     ebx, ebx
0x1800082f6  test    r14, r14
0x1800082f9  jz      short loc_180008368
0x1800082fb  lea     r8, [rbp+pDefault]; pDefault
0x1800082ff  mov     [rbp+pDefault.DesiredAccess], 20008h
0x180008306  lea     rdx, [rbp+phPrinter]; phPrinter
0x18000830a  mov     rcx, r15; pPrinterName
0x18000830d  call    cs:__imp_OpenPrinterW
0x180008313  test    eax, eax
0x180008315  jz      short loc_180008368
0x180008317  mov     rcx, [rbp+phPrinter]; hPrinter
0x18000831b  lea     r8, [rbp+hMem]; unsigned __int8 **
0x18000831f  lea     edx, [rbx+2]; Level
0x180008322  mov     [rbp+hMem], rbx
0x180008326  call    ?GetPrinterAlloc@@YAHPEAXKPEAPEAE@Z; GetPrinterAlloc(void *,ulong,uchar * *)
0x18000832b  test    eax, eax
0x18000832d  jz      short loc_18000835E
0x18000832f  mov     r11, [rbp+hMem]
0x180008333  xor     eax, eax
0x180008335  mov     [r14], ax
0x180008339  test    r11, r11
0x18000833c  jz      short loc_180008355
0x18000833e  mov     r8, [r11]; unsigned __int16 *
0x180008341  test    r8, r8
0x180008344  jz      short loc_180008355
0x180008346  mov     edx, 104h; unsigned __int64
0x18000834b  mov     rcx, r14; unsigned __int16 *
0x18000834e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008353  mov     ebx, eax
0x180008355  mov     rcx, r11; hMem
0x180008358  call    cs:__imp_LocalFree
0x18000835e  mov     rcx, [rbp+phPrinter]; hPrinter
0x180008362  call    cs:__imp_ClosePrinter
0x180008368  mov     eax, ebx
0x18000836a  add     rsp, 68h
0x18000836e  pop     r15
0x180008370  pop     r14
0x180008372  pop     rdi
0x180008373  pop     rsi
0x180008374  pop     rbx
0x180008375  pop     rbp
0x180008376  retn
0x180008377  test    eax, eax
0x180008379  jle     short loc_180008368
0x18000837b  movzx   ebx, ax
0x18000837e  or      ebx, 80070000h
0x180008384  jmp     short loc_180008368
```

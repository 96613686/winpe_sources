# ClosePrintProcessor

- ea: `0x180002fc0`
- end: `0x18000311e`
- name: `ClosePrintProcessor`
- size: `350`
- prototype: `BOOL __stdcall(HANDLE hPrintProcessor)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002fc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800030b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800030b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800030bb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003090`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800030c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800030d1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800030e7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800030f2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800030fd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003108`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003113`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003090`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800030c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800030d1`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800030e7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800030f2`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800030fd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003108`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180003113`
- `GDI32!DeleteDC` at `0x1800030dc`
- `GDI32!DeleteDC` at `0x1800030dc`
- `WINSPOOL!ClosePrinter` at `0x1800030a1`
- `WINSPOOL!ClosePrinter` at `0x1800030a1`

## pseudocode

```c
BOOL __stdcall ClosePrintProcessor(HANDLE hPrintProcessor)
{
  void *v2; // rcx
  HDC v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx

  if ( (char *)hPrintProcessor - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && *(_DWORD *)hPrintProcessor == 20561 )
  {
    *(_DWORD *)hPrintProcessor = 0;
    v2 = (void *)*((_QWORD *)hPrintProcessor + 5);
    if ( v2 )
      ClosePrinter(v2);
    v3 = (HDC)*((_QWORD *)hPrintProcessor + 13);
    if ( v3 )
      DeleteDC(v3);
    v4 = (void *)*((_QWORD *)hPrintProcessor + 14);
    if ( v4 )
      LocalFree(v4);
    v5 = (void *)*((_QWORD *)hPrintProcessor + 15);
    if ( v5 )
      LocalFree(v5);
    v6 = (void *)*((_QWORD *)hPrintProcessor + 3);
    if ( v6 )
      CloseHandle(v6);
    v7 = (void *)*((_QWORD *)hPrintProcessor + 6);
    if ( v7 )
      LocalFree(v7);
    v8 = (void *)*((_QWORD *)hPrintProcessor + 9);
    if ( v8 )
      LocalFree(v8);
    v9 = (void *)*((_QWORD *)hPrintProcessor + 7);
    if ( v9 )
      LocalFree(v9);
    v10 = (void *)*((_QWORD *)hPrintProcessor + 8);
    if ( v10 )
      LocalFree(v10);
    v11 = (void *)*((_QWORD *)hPrintProcessor + 10);
    if ( v11 )
      LocalFree(v11);
    *(_OWORD *)hPrintProcessor = 0;
    *((_OWORD *)hPrintProcessor + 1) = 0;
    *((_OWORD *)hPrintProcessor + 2) = 0;
    *((_OWORD *)hPrintProcessor + 3) = 0;
    *((_OWORD *)hPrintProcessor + 4) = 0;
    *((_OWORD *)hPrintProcessor + 5) = 0;
    *((_OWORD *)hPrintProcessor + 6) = 0;
    *((_OWORD *)hPrintProcessor + 7) = 0;
    LocalFree(hPrintProcessor);
    return 1;
  }
  else
  {
    SetLastError(6u);
    return 0;
  }
}

```

## disassembly

```asm
0x180002fc0  push    rbx
0x180002fc2  sub     rsp, 20h
0x180002fc6  lea     rax, [rcx-1]
0x180002fca  mov     rbx, rcx
0x180002fcd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002fd1  ja      loc_1800030AC
0x180002fd7  cmp     dword ptr [rcx], 5051h
0x180002fdd  jnz     loc_1800030AC
0x180002fe3  mov     dword ptr [rcx], 0
0x180002fe9  mov     rcx, [rcx+28h]; hPrinter
0x180002fed  test    rcx, rcx
0x180002ff0  jnz     loc_1800030A1
0x180002ff6  mov     rcx, [rbx+68h]; hdc
0x180002ffa  test    rcx, rcx
0x180002ffd  jnz     loc_1800030DC
0x180003003  mov     rcx, [rbx+70h]; hMem
0x180003007  test    rcx, rcx
0x18000300a  jnz     loc_1800030E7
0x180003010  mov     rcx, [rbx+78h]; hMem
0x180003014  test    rcx, rcx
0x180003017  jnz     loc_1800030C6
0x18000301d  mov     rcx, [rbx+18h]; hObject
0x180003021  test    rcx, rcx
0x180003024  jnz     loc_1800030BB
0x18000302a  mov     rcx, [rbx+30h]; hMem
0x18000302e  test    rcx, rcx
0x180003031  jnz     loc_1800030D1
0x180003037  mov     rcx, [rbx+48h]; hMem
0x18000303b  test    rcx, rcx
0x18000303e  jnz     loc_1800030F2
0x180003044  mov     rcx, [rbx+38h]; hMem
0x180003048  test    rcx, rcx
0x18000304b  jnz     loc_1800030FD
0x180003051  mov     rcx, [rbx+40h]; hMem
0x180003055  test    rcx, rcx
0x180003058  jnz     loc_180003108
0x18000305e  mov     rcx, [rbx+50h]; hMem
0x180003062  test    rcx, rcx
0x180003065  jnz     loc_180003113
0x18000306b  xorps   xmm0, xmm0
0x18000306e  mov     rcx, rbx; hMem
0x180003071  movups  xmmword ptr [rbx], xmm0
0x180003074  movups  xmmword ptr [rbx+10h], xmm0
0x180003078  movups  xmmword ptr [rbx+20h], xmm0
0x18000307c  movups  xmmword ptr [rbx+30h], xmm0
0x180003080  movups  xmmword ptr [rbx+40h], xmm0
0x180003084  movups  xmmword ptr [rbx+50h], xmm0
0x180003088  movups  xmmword ptr [rbx+60h], xmm0
0x18000308c  movups  xmmword ptr [rbx+70h], xmm0
0x180003090  call    cs:__imp_LocalFree
0x180003096  mov     eax, 1
0x18000309b  add     rsp, 20h
0x18000309f  pop     rbx
0x1800030a0  retn
0x1800030a1  call    cs:__imp_ClosePrinter
0x1800030a7  jmp     loc_180002FF6
0x1800030ac  mov     ecx, 6; dwErrCode
0x1800030b1  call    cs:__imp_SetLastError
0x1800030b7  xor     eax, eax
0x1800030b9  jmp     short loc_18000309B
0x1800030bb  call    cs:__imp_CloseHandle
0x1800030c1  jmp     loc_18000302A
0x1800030c6  call    cs:__imp_LocalFree
0x1800030cc  jmp     loc_18000301D
0x1800030d1  call    cs:__imp_LocalFree
0x1800030d7  jmp     loc_180003037
0x1800030dc  call    cs:__imp_DeleteDC
0x1800030e2  jmp     loc_180003003
0x1800030e7  call    cs:__imp_LocalFree
0x1800030ed  jmp     loc_180003010
0x1800030f2  call    cs:__imp_LocalFree
0x1800030f8  jmp     loc_180003044
0x1800030fd  call    cs:__imp_LocalFree
0x180003103  jmp     loc_180003051
0x180003108  call    cs:__imp_LocalFree
0x18000310e  jmp     loc_18000305E
0x180003113  call    cs:__imp_LocalFree
0x180003119  jmp     loc_18000306B
```

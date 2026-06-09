# GetPrinterInfo(void *,ulong,ulong *)

- ea: `0x180006100`
- end: `0x1800061e5`
- name: `?GetPrinterInfo@@YAPEAEPEAXKPEAK@Z`
- size: `229`
- prototype: `unsigned __int8 *__fastcall(HANDLE hPrinter, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003390`

## callees

- `0x180006100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006172`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180006132`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180006191`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180006132`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180006191`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180006182`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800061ad`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800061c0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180006182`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800061ad`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800061c0`
- `WINSPOOL!GetPrinterW` at `0x180006167`
- `WINSPOOL!GetPrinterW` at `0x180006167`

## pseudocode

```c
unsigned __int8 *__fastcall GetPrinterInfo(HANDLE hPrinter, __int64 a2, unsigned int *a3)
{
  DWORD v4; // ebp
  BYTE *v6; // rbx
  __int16 i; // si
  DWORD LastError; // eax
  DWORD pcbNeeded; // [rsp+68h] [rbp+10h] BYREF

  v4 = 2048;
  pcbNeeded = 0;
  v6 = (BYTE *)LocalAlloc(0x40u, 0x800u);
  if ( v6 )
  {
    for ( i = 2; i; --i )
    {
      if ( GetPrinterW(hPrinter, 2u, v6, v4, &pcbNeeded) )
      {
        *a3 = 0;
        return v6;
      }
      LastError = GetLastError();
      *a3 = LastError;
      if ( LastError != 122 )
      {
        LocalFree(v6);
        return 0;
      }
      LocalFree(v6);
      v6 = (BYTE *)LocalAlloc(0x40u, pcbNeeded);
      if ( !v6 )
        goto LABEL_11;
      v4 = pcbNeeded;
    }
    LocalFree(v6);
  }
LABEL_11:
  *a3 = 8;
  return 0;
}

```

## disassembly

```asm
0x180006100  mov     rax, rsp
0x180006103  mov     [rax+8], rbx
0x180006107  mov     [rax+18h], rbp
0x18000610b  mov     [rax+10h], edx
0x18000610e  push    rsi
0x18000610f  push    rdi
0x180006110  push    r12
0x180006112  push    r14
0x180006114  push    r15
0x180006116  sub     rsp, 30h
0x18000611a  xor     r15d, r15d
0x18000611d  mov     r14, rcx
0x180006120  mov     ebp, 800h
0x180006125  mov     [rax+10h], r15d
0x180006129  mov     edx, ebp; uBytes
0x18000612b  mov     rdi, r8
0x18000612e  lea     ecx, [r15+40h]; uFlags
0x180006132  call    cs:__imp_LocalAlloc
0x180006138  mov     rbx, rax
0x18000613b  test    rax, rax
0x18000613e  jz      loc_1800061C6
0x180006144  lea     r12d, [r15+2]
0x180006148  movzx   esi, r12w
0x18000614c  test    si, si
0x18000614f  jz      short loc_1800061BD
0x180006151  lea     rax, [rsp+58h+arg_8]
0x180006156  mov     r9d, ebp; cbBuf
0x180006159  mov     r8, rbx; pPrinter
0x18000615c  mov     [rsp+58h+pcbNeeded], rax; pcbNeeded
0x180006161  mov     edx, r12d; Level
0x180006164  mov     rcx, r14; hPrinter
0x180006167  call    cs:__imp_GetPrinterW
0x18000616d  cmp     eax, 1
0x180006170  jz      short loc_1800061B5
0x180006172  call    cs:__imp_GetLastError
0x180006178  mov     [rdi], eax
0x18000617a  mov     rcx, rbx; hMem
0x18000617d  cmp     eax, 7Ah ; 'z'
0x180006180  jnz     short loc_1800061AD
0x180006182  call    cs:__imp_LocalFree
0x180006188  mov     edx, [rsp+58h+arg_8]; uBytes
0x18000618c  mov     ecx, 40h ; '@'; uFlags
0x180006191  call    cs:__imp_LocalAlloc
0x180006197  mov     rbx, rax
0x18000619a  test    rax, rax
0x18000619d  jz      short loc_1800061C6
0x18000619f  mov     ebp, [rsp+58h+arg_8]
0x1800061a3  mov     eax, 0FFFFh
0x1800061a8  add     si, ax
0x1800061ab  jmp     short loc_18000614C
0x1800061ad  call    cs:__imp_LocalFree
0x1800061b3  jmp     short loc_1800061CC
0x1800061b5  mov     [rdi], r15d
0x1800061b8  mov     rax, rbx
0x1800061bb  jmp     short loc_1800061CE
0x1800061bd  mov     rcx, rbx; hMem
0x1800061c0  call    cs:__imp_LocalFree
0x1800061c6  mov     dword ptr [rdi], 8
0x1800061cc  xor     eax, eax
0x1800061ce  mov     rbx, [rsp+58h+arg_0]
0x1800061d3  mov     rbp, [rsp+58h+arg_10]
0x1800061d8  add     rsp, 30h
0x1800061dc  pop     r15
0x1800061de  pop     r14
0x1800061e0  pop     r12
0x1800061e2  pop     rdi
0x1800061e3  pop     rsi
0x1800061e4  retn
```

# CUmRdpPrn::RegisterPrinterConfigChangeNotification(ulong)

- ea: `0x180005f60`
- end: `0x18000615d`
- name: `?RegisterPrinterConfigChangeNotification@CUmRdpPrn@@AEAAHK@Z`
- size: `509`
- prototype: `__int64 __fastcall(CUmRdpPrn *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007f4c`

## callees

- `0x180005f60`
- `0x180019734`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006138`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006018`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006018`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006005`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006005`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000606a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000606a`
- `WINSPOOL!OpenPrinterW` at `0x1800060a9`
- `WINSPOOL!OpenPrinterW` at `0x1800060a9`
- `WINSPOOL!ClosePrinter` at `0x180006052`
- `WINSPOOL!ClosePrinter` at `0x180006052`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x1800060cb`
- `WINSPOOL!FindFirstPrinterChangeNotification` at `0x1800060cb`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x180006044`
- `WINSPOOL!FindClosePrinterChangeNotification` at `0x180006044`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::RegisterPrinterConfigChangeNotification(CUmRdpPrn *this, int a2)
{
  __int64 v2; // r10
  unsigned int v4; // r9d
  unsigned int v6; // r8d
  __int64 v7; // rbp
  WCHAR *v8; // rdi
  char *v9; // rax
  char *v10; // rbx
  unsigned int v11; // edi
  HANDLE *v12; // r14
  HANDLE v14; // rcx
  HANDLE v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // r8d
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+20h] [rbp-38h] BYREF

  v2 = *((_QWORD *)this + 5);
  memset(&pDefault, 0, sizeof(pDefault));
  v4 = *(_DWORD *)(v2 + 8);
  v6 = 0;
  if ( v4 )
  {
    while ( *(_DWORD *)(*(_QWORD *)v2 + 80LL * v6 + 4) != a2 )
    {
      if ( ++v6 >= v4 )
        goto LABEL_4;
    }
  }
  else
  {
LABEL_4:
    if ( v6 >= v4 )
      return 0;
  }
  v7 = 10LL * v6;
  if ( !*(_QWORD *)(*(_QWORD *)v2 + 80LL * v6 + 72) )
  {
    v8 = *(WCHAR **)(*(_QWORD *)v2 + 80LL * v6 + 24);
    pDefault.DesiredAccess = 983052;
    v9 = (char *)HeapAlloc(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
    v10 = v9;
    if ( v9 )
    {
      v12 = (HANDLE *)(v9 + 8);
      *((_QWORD *)v9 + 1) = 0;
      *(_QWORD *)v9 = 0;
      *((_DWORD *)v9 + 4) = a2;
      v11 = OpenPrinterW(v8, (LPHANDLE)v9 + 1, &pDefault);
      if ( v11 )
      {
        v14 = *v12;
        *((_QWORD *)v10 + 3) = this;
        v15 = FindFirstPrinterChangeNotification(v14, 0x70000004u, 0, 0);
        *(_QWORD *)v10 = v15;
        if ( !v15 )
        {
          GetLastError();
          v11 = 0;
          goto LABEL_9;
        }
        v16 = *((_QWORD *)this + 15);
        v17 = *(unsigned int *)(v16 + 1536);
        if ( (unsigned int)v17 >= 0x40 )
        {
          v18 = 122;
        }
        else
        {
          *(_QWORD *)(v16 + 8 * v17 + 512) = v15;
          *(_QWORD *)(v16 + 8 * v17) = CUmRdpPrn::staticSinglePrinterNotifyObjectSignaled;
          v18 = 0;
          *(_QWORD *)(v16 + 8 * v17 + 1024) = v10;
          ++*(_DWORD *)(v16 + 1536);
        }
        v11 = v18 == 0;
        if ( v18 )
          goto LABEL_9;
        *(_QWORD *)(**((_QWORD **)this + 5) + 8 * v7 + 72) = v10;
        return v11;
      }
    }
    else
    {
      SetLastError(0xEu);
      v11 = 0;
      v12 = (HANDLE *)8;
    }
    GetLastError();
    if ( v10 )
    {
LABEL_9:
      if ( *(_QWORD *)v10 )
      {
        WTBLOBJ_RemoveWaitableObject(*((void **)this + 15), *(void **)v10);
        FindClosePrinterChangeNotification(*(HANDLE *)v10);
      }
      if ( *v12 )
        ClosePrinter(*v12);
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, v10);
      return v11;
    }
    return v11;
  }
  return 1;
}

```

## disassembly

```asm
0x180005f60  push    rsi
0x180005f62  push    r12
0x180005f64  push    r15
0x180005f66  sub     rsp, 40h
0x180005f6a  mov     r10, [rcx+28h]
0x180005f6e  xor     eax, eax
0x180005f70  xor     r12d, r12d
0x180005f73  mov     qword ptr [rsp+58h+pDefault.DesiredAccess], rax
0x180005f78  xorps   xmm0, xmm0
0x180005f7b  mov     r15d, edx
0x180005f7e  movups  xmmword ptr [rsp+58h+pDefault.pDatatype], xmm0
0x180005f83  mov     r9d, [r10+8]
0x180005f87  mov     rsi, rcx
0x180005f8a  mov     r8d, r12d
0x180005f8d  test    r9d, r9d
0x180005f90  jz      short loc_180005FAE
0x180005f92  mov     rdx, [r10]
0x180005f95  mov     eax, r8d
0x180005f98  lea     rcx, [rax+rax*4]
0x180005f9c  add     rcx, rcx
0x180005f9f  cmp     [rdx+rcx*8+4], r15d
0x180005fa4  jz      short loc_180005FB7
0x180005fa6  inc     r8d
0x180005fa9  cmp     r8d, r9d
0x180005fac  jb      short loc_180005F95
0x180005fae  cmp     r8d, r9d
0x180005fb1  jnb     loc_180006150
0x180005fb7  mov     eax, r8d
0x180005fba  mov     [rsp+58h+arg_8], rbp
0x180005fbf  lea     rbp, [rax+rax*4]
0x180005fc3  mov     rax, [r10]
0x180005fc6  add     rbp, rbp
0x180005fc9  cmp     [rax+rbp*8+48h], r12
0x180005fce  jnz     loc_180006146
0x180005fd4  mov     [rsp+58h+arg_0], rbx
0x180005fd9  xor     edx, edx; dwFlags
0x180005fdb  mov     [rsp+58h+arg_10], rdi
0x180005fe0  mov     r8d, 20h ; ' '; dwBytes
0x180005fe6  mov     rdi, [rax+rbp*8+18h]
0x180005feb  mov     [rsp+58h+pDefault.DesiredAccess], 0F000Ch
0x180005ff3  mov     rcx, gs:60h
0x180005ffc  mov     [rsp+58h+arg_18], r14
0x180006001  mov     rcx, [rcx+30h]; hHeap
0x180006005  call    cs:__imp_HeapAlloc
0x18000600b  mov     rbx, rax
0x18000600e  test    rax, rax
0x180006011  jnz     short loc_180006090
0x180006013  mov     ecx, 0Eh; dwErrCode
0x180006018  call    cs:__imp_SetLastError
0x18000601e  mov     edi, r12d
0x180006021  lea     r14, [rbx+8]
0x180006025  call    cs:__imp_GetLastError
0x18000602b  test    rbx, rbx
0x18000602e  jz      short loc_180006070
0x180006030  mov     rdx, [rbx]; void *
0x180006033  test    rdx, rdx
0x180006036  jz      short loc_18000604A
0x180006038  mov     rcx, [rsi+78h]; void *
0x18000603c  call    ?WTBLOBJ_RemoveWaitableObject@@YAXPEAX0@Z; WTBLOBJ_RemoveWaitableObject(void *,void *)
0x180006041  mov     rcx, [rbx]; hChange
0x180006044  call    cs:__imp_FindClosePrinterChangeNotification
0x18000604a  mov     rcx, [r14]; hPrinter
0x18000604d  test    rcx, rcx
0x180006050  jz      short loc_180006058
0x180006052  call    cs:__imp_ClosePrinter
0x180006058  mov     rcx, gs:60h
0x180006061  mov     r8, rbx; lpMem
0x180006064  xor     edx, edx; dwFlags
0x180006066  mov     rcx, [rcx+30h]; hHeap
0x18000606a  call    cs:__imp_HeapFree
0x180006070  mov     r14, [rsp+58h+arg_18]
0x180006075  mov     eax, edi
0x180006077  mov     rdi, [rsp+58h+arg_10]
0x18000607c  mov     rbx, [rsp+58h+arg_0]
0x180006081  mov     rbp, [rsp+58h+arg_8]
0x180006086  add     rsp, 40h
0x18000608a  pop     r15
0x18000608c  pop     r12
0x18000608e  pop     rsi
0x18000608f  retn
0x180006090  lea     r14, [rax+8]
0x180006094  mov     rcx, rdi; pPrinterName
0x180006097  lea     r8, [rsp+58h+pDefault]; pDefault
0x18000609c  mov     [r14], r12
0x18000609f  mov     rdx, r14; phPrinter
0x1800060a2  mov     [rax], r12
0x1800060a5  mov     [rax+10h], r15d
0x1800060a9  call    cs:__imp_OpenPrinterW
0x1800060af  mov     edi, eax
0x1800060b1  test    eax, eax
0x1800060b3  jz      loc_180006025
0x1800060b9  mov     rcx, [r14]; hPrinter
0x1800060bc  xor     r9d, r9d; pPrinterNotifyOptions
0x1800060bf  xor     r8d, r8d; fdwOptions
0x1800060c2  mov     [rbx+18h], rsi
0x1800060c6  mov     edx, 70000004h; fdwFilter
0x1800060cb  call    cs:__imp_FindFirstPrinterChangeNotification
0x1800060d1  mov     [rbx], rax
0x1800060d4  test    rax, rax
0x1800060d7  jz      short loc_180006138
0x1800060d9  mov     rdx, [rsi+78h]
0x1800060dd  mov     ecx, [rdx+600h]
0x1800060e3  cmp     ecx, 40h ; '@'
0x1800060e6  jnb     short loc_18000610E
0x1800060e8  lea     r9, ?staticSinglePrinterNotifyObjectSignaled@CUmRdpPrn@@CAXPEAXPEAUtagPRINTNOTIFYREC@@@Z; CUmRdpPrn::staticSinglePrinterNotifyObjectSignaled(void *,tagPRINTNOTIFYREC *)
0x1800060ef  mov     [rdx+rcx*8+200h], rax
0x1800060f7  mov     [rdx+rcx*8], r9
0x1800060fb  mov     r8d, r12d
0x1800060fe  mov     [rdx+rcx*8+400h], rbx
0x180006106  inc     dword ptr [rdx+600h]
0x18000610c  jmp     short loc_180006114
0x18000610e  mov     r8d, 7Ah ; 'z'
0x180006114  test    r8d, r8d
0x180006117  mov     edi, r12d
0x18000611a  setz    dil
0x18000611e  test    r8d, r8d
0x180006121  jnz     loc_180006030
0x180006127  mov     rcx, [rsi+28h]
0x18000612b  mov     rdx, [rcx]
0x18000612e  mov     [rdx+rbp*8+48h], rbx
0x180006133  jmp     loc_180006070
0x180006138  call    cs:__imp_GetLastError
0x18000613e  mov     edi, r12d
0x180006141  jmp     loc_180006030
0x180006146  mov     eax, 1
0x18000614b  jmp     loc_180006081
0x180006150  mov     eax, r12d
0x180006153  add     rsp, 40h
0x180006157  pop     r15
0x180006159  pop     r12
0x18000615b  pop     rsi
0x18000615c  retn
```

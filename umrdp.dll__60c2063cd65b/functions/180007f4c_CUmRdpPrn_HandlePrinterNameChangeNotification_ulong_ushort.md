# CUmRdpPrn::HandlePrinterNameChangeNotification(ulong,ushort *)

- ea: `0x180007f4c`
- end: `0x1800082d9`
- name: `?HandlePrinterNameChangeNotification@CUmRdpPrn@@AEAAHKPEAG@Z`
- size: `909`
- prototype: `__int64 __fastcall(CUmRdpPrn *__hidden this, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180007dd0`
- `0x1800153cc`

## callees

- `0x180005f60`
- `0x180007f4c`
- `0x180009fa8`
- `0x18000a200`
- `0x18000a3ac`
- `0x18000a574`
- `0x1800140a4`
- `0x180014fdc`
- `0x180016f38`
- `0x180017288`
- `0x1800197e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800081ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000809e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008152`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000809e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008152`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180008066`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000811a`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180008066`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000811a`
- `WINSPOOL!OpenPrinterW` at `0x1800081bb`
- `WINSPOOL!OpenPrinterW` at `0x1800081bb`
- `WINSPOOL!ClosePrinter` at `0x1800082b8`
- `WINSPOOL!ClosePrinter` at `0x1800082b8`

## pseudocode

```c
__int64 __fastcall CUmRdpPrn::HandlePrinterNameChangeNotification(
        CUmRdpPrn *this,
        unsigned int a2,
        unsigned __int16 *a3)
{
  __int64 v3; // rax
  struct tagDRDEVLST *v8; // r15
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned int PrinterPortName; // edi
  __int64 v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // esi
  LPVOID v16; // rax
  __int64 v17; // r8
  _QWORD *v18; // rax
  unsigned __int16 *v19; // rcx
  LPVOID v20; // rax
  __int64 v21; // r8
  _QWORD *v22; // rax
  unsigned __int16 *v23; // rcx
  struct tagDRDEVLST *v24; // r15
  __int64 v25; // rcx
  int v26; // edx
  HANDLE phPrinter; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-28h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v30; // [rsp+A0h] [rbp+30h] BYREF
  unsigned int v31; // [rsp+B8h] [rbp+48h] BYREF

  v3 = *(_QWORD *)this;
  phPrinter = 0;
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  v30 = 0;
  v28 = 0;
  v31 = 0;
  if ( *(_DWORD *)(v3 + 2168) )
    return 0;
  v8 = (struct tagDRDEVLST *)*((_QWORD *)this + 5);
  if ( (unsigned int)DRDEVLST_FindByServerDeviceName(v8, a3, &v31) )
  {
    v9 = 10LL * v31;
    if ( *(_DWORD *)(*(_QWORD *)v8 + 80LL * v31 + 8) == 4 )
    {
      *(_DWORD *)(*(_QWORD *)v8 + 80LL * v31 + 4) = a2;
      v10 = *(_QWORD *)(**((_QWORD **)this + 5) + 8 * v9 + 72);
      if ( v10 && *(_DWORD *)(v10 + 16) != a2 )
        *(_DWORD *)(v10 + 16) = a2;
      PrinterPortName = CUmRdpPrn::RegisterPrinterConfigChangeNotification(this, a2);
      goto LABEL_38;
    }
  }
  if ( !(unsigned int)DRDEVLST_FindByServerDeviceID(v8, a2, &v30) )
  {
    PrinterPortName = OpenPrinterW(a3, &phPrinter, &pDefault);
    if ( PrinterPortName )
    {
      PrinterPortName = CUmRdpPrn::GetPrinterPortName(this, phPrinter, &v28);
      if ( PrinterPortName )
      {
        v24 = (struct tagDRDEVLST *)*((_QWORD *)this + 5);
        if ( (unsigned int)DRDEVLST_FindByServerDeviceName(v24, v28, &v30) )
        {
          v25 = 80LL * v30;
          v26 = *(_DWORD *)(v25 + *(_QWORD *)v24 + 8);
          if ( (unsigned int)(v26 - 1) <= 1 || v26 == 16 )
          {
            CUmRdpPrn::SendAddPrinterMsgToClient(
              this,
              a3,
              *(const unsigned __int16 **)(*((_QWORD *)this + 25) + 32LL),
              (const char *)(*(_QWORD *)v24 + v25 + 52));
            AddSessionIDToPrinterQueue(phPrinter, **(_DWORD **)this);
            PrinterPortName = DRDEVLST_Add(*((struct tagDRDEVLST **)this + 5), -1, a2, 4, a3, a3, "UNKNOWN");
            if ( PrinterPortName )
              CUmRdpPrn::RegisterPrinterConfigChangeNotification(this, a2);
          }
        }
        goto LABEL_38;
      }
    }
    else
    {
      if ( *(_DWORD *)(*(_QWORD *)this + 2168LL) )
        goto LABEL_38;
      if ( GetLastError() == 1801 )
      {
        GetLastError();
        goto LABEL_25;
      }
    }
    GetLastError();
    goto LABEL_38;
  }
  v12 = 10LL * v30;
  v13 = *(_QWORD *)(*(_QWORD *)v8 + 80LL * v30 + 72);
  if ( v13 && *(_DWORD *)(v13 + 16) != a2 )
    *(_DWORD *)(v13 + 16) = a2;
  v14 = -1;
  do
    ++v14;
  while ( a3[v14] );
  v15 = v14 + 1;
  v16 = HeapReAlloc(
          NtCurrentPeb()->ProcessHeap,
          0,
          *(LPVOID *)(**((_QWORD **)this + 5) + 8 * v12 + 24),
          2LL * (unsigned int)(v14 + 1));
  v17 = **((_QWORD **)this + 5);
  if ( v16 )
  {
    *(_QWORD *)(v17 + 8 * v12 + 24) = v16;
    *(_DWORD *)(**((_QWORD **)this + 5) + 8 * v12 + 32) = v15;
  }
  else
  {
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, *(LPVOID *)(v17 + 8 * v12 + 24));
    *(_QWORD *)(**((_QWORD **)this + 5) + 8 * v12 + 24) = 0;
    *(_DWORD *)(**((_QWORD **)this + 5) + 8 * v12 + 32) = 0;
  }
  v18 = (_QWORD *)*((_QWORD *)this + 5);
  v19 = *(unsigned __int16 **)(*v18 + 8 * v12 + 24);
  if ( !v19 )
  {
    TsLogError(&EVENT_NOTIFY_INSUFFICIENTRESOURCES, 0, 0);
    PrinterPortName = 0;
    goto LABEL_38;
  }
  StringCchCopyW(v19, *(unsigned int *)(*v18 + 8 * v12 + 32), a3);
  if ( CUmRdpPrn::SendPrinterRenameToClient(
         this,
         *(const unsigned __int16 **)(**((_QWORD **)this + 5) + 8 * v12 + 40),
         a3) )
  {
    v20 = HeapReAlloc(NtCurrentPeb()->ProcessHeap, 0, *(LPVOID *)(**((_QWORD **)this + 5) + 8 * v12 + 40), 2LL * v15);
    v21 = **((_QWORD **)this + 5);
    if ( v20 )
    {
      *(_QWORD *)(v21 + 8 * v12 + 40) = v20;
      *(_DWORD *)(**((_QWORD **)this + 5) + 8 * v12 + 48) = v15;
    }
    else
    {
      HeapFree(NtCurrentPeb()->ProcessHeap, 0, *(LPVOID *)(v21 + 8 * v12 + 40));
      *(_QWORD *)(**((_QWORD **)this + 5) + 8 * v12 + 40) = 0;
      *(_DWORD *)(**((_QWORD **)this + 5) + 8 * v12 + 48) = 0;
    }
    v22 = (_QWORD *)*((_QWORD *)this + 5);
    v23 = *(unsigned __int16 **)(*v22 + 8 * v12 + 40);
    if ( v23 )
      StringCchCopyW(v23, *(unsigned int *)(*v22 + 8 * v12 + 48), a3);
  }
LABEL_25:
  PrinterPortName = 1;
LABEL_38:
  if ( phPrinter )
    ClosePrinter(phPrinter);
  return PrinterPortName;
}

```

## disassembly

```asm
0x180007f4c  mov     [rsp-28h+arg_8], rbx
0x180007f51  mov     [rsp-28h+arg_10], rsi
0x180007f56  push    rbp
0x180007f57  push    rdi
0x180007f58  push    r12
0x180007f5a  push    r14
0x180007f5c  push    r15
0x180007f5e  mov     rbp, rsp
0x180007f61  sub     rsp, 70h
0x180007f65  mov     rax, [rcx]
0x180007f68  xor     r12d, r12d
0x180007f6b  xorps   xmm0, xmm0
0x180007f6e  mov     [rbp+phPrinter], r12
0x180007f72  movdqu  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x180007f77  mov     qword ptr [rbp+pDefault.DesiredAccess], 0F000Ch
0x180007f7f  mov     r14, r8
0x180007f82  mov     esi, edx
0x180007f84  mov     rbx, rcx
0x180007f87  mov     [rbp+arg_0], r12d
0x180007f8b  mov     [rbp+var_28], r12
0x180007f8f  mov     [rbp+arg_18], r12d
0x180007f93  cmp     [rax+878h], r12d
0x180007f9a  jz      short loc_180007FA3
0x180007f9c  xor     eax, eax
0x180007f9e  jmp     loc_1800082C0
0x180007fa3  mov     r15, [rcx+28h]
0x180007fa7  lea     r8, [rbp+arg_18]; unsigned int *
0x180007fab  mov     rcx, r15; struct tagDRDEVLST *
0x180007fae  mov     rdx, r14; unsigned __int16 *
0x180007fb1  call    ?DRDEVLST_FindByServerDeviceName@@YAHPEAUtagDRDEVLST@@PEBGPEAK@Z; DRDEVLST_FindByServerDeviceName(tagDRDEVLST *,ushort const *,ulong *)
0x180007fb6  test    eax, eax
0x180007fb8  jz      short loc_180007FFC
0x180007fba  mov     eax, [rbp+arg_18]
0x180007fbd  lea     rdx, [rax+rax*4]
0x180007fc1  mov     rax, [r15]
0x180007fc4  add     rdx, rdx
0x180007fc7  cmp     dword ptr [rax+rdx*8+8], 4
0x180007fcc  jnz     short loc_180007FFC
0x180007fce  mov     [rax+rdx*8+4], esi
0x180007fd2  mov     rax, [rbx+28h]
0x180007fd6  mov     rcx, [rax]
0x180007fd9  mov     rax, [rcx+rdx*8+48h]
0x180007fde  test    rax, rax
0x180007fe1  jz      short loc_180007FEB
0x180007fe3  cmp     [rax+10h], esi
0x180007fe6  jz      short loc_180007FEB
0x180007fe8  mov     [rax+10h], esi
0x180007feb  mov     edx, esi; unsigned int
0x180007fed  mov     rcx, rbx; this
0x180007ff0  call    ?RegisterPrinterConfigChangeNotification@CUmRdpPrn@@AEAAHK@Z; CUmRdpPrn::RegisterPrinterConfigChangeNotification(ulong)
0x180007ff5  mov     edi, eax
0x180007ff7  jmp     loc_1800082AF
0x180007ffc  lea     r8, [rbp+arg_0]; unsigned int *
0x180008000  mov     edx, esi; unsigned int
0x180008002  mov     rcx, r15; struct tagDRDEVLST *
0x180008005  call    ?DRDEVLST_FindByServerDeviceID@@YAHPEAUtagDRDEVLST@@KPEAK@Z; DRDEVLST_FindByServerDeviceID(tagDRDEVLST *,ulong,ulong *)
0x18000800a  test    eax, eax
0x18000800c  jz      loc_1800081B0
0x180008012  mov     eax, [rbp+arg_0]
0x180008015  lea     rdi, [rax+rax*4]
0x180008019  mov     rax, [r15]
0x18000801c  add     rdi, rdi
0x18000801f  mov     rcx, [rax+rdi*8+48h]
0x180008024  test    rcx, rcx
0x180008027  jz      short loc_180008031
0x180008029  cmp     [rcx+10h], esi
0x18000802c  jz      short loc_180008031
0x18000802e  mov     [rcx+10h], esi
0x180008031  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008035  inc     rax
0x180008038  cmp     [r14+rax*2], r12w
0x18000803d  jnz     short loc_180008035
0x18000803f  mov     rcx, gs:60h
0x180008048  lea     esi, [rax+1]
0x18000804b  mov     rax, [rbx+28h]
0x18000804f  xor     edx, edx; dwFlags
0x180008051  mov     r15d, esi
0x180008054  add     r15, r15
0x180008057  mov     rcx, [rcx+30h]; hHeap
0x18000805b  mov     r9, r15; dwBytes
0x18000805e  mov     r8, [rax]
0x180008061  mov     r8, [r8+rdi*8+18h]; lpMem
0x180008066  call    cs:__imp_HeapReAlloc
0x18000806c  mov     rcx, [rbx+28h]
0x180008070  mov     r8, [rcx]
0x180008073  test    rax, rax
0x180008076  jz      short loc_18000808A
0x180008078  mov     [r8+rdi*8+18h], rax
0x18000807d  mov     rax, [rbx+28h]
0x180008081  mov     rcx, [rax]
0x180008084  mov     [rcx+rdi*8+20h], esi
0x180008088  jmp     short loc_1800080BC
0x18000808a  mov     rcx, gs:60h
0x180008093  xor     edx, edx; dwFlags
0x180008095  mov     r8, [r8+rdi*8+18h]; lpMem
0x18000809a  mov     rcx, [rcx+30h]; hHeap
0x18000809e  call    cs:__imp_HeapFree
0x1800080a4  mov     rax, [rbx+28h]
0x1800080a8  mov     rcx, [rax]
0x1800080ab  mov     [rcx+rdi*8+18h], r12
0x1800080b0  mov     rax, [rbx+28h]
0x1800080b4  mov     rcx, [rax]
0x1800080b7  mov     [rcx+rdi*8+20h], r12d
0x1800080bc  mov     rax, [rbx+28h]
0x1800080c0  mov     rdx, [rax]
0x1800080c3  mov     rcx, [rdx+rdi*8+18h]; unsigned __int16 *
0x1800080c8  test    rcx, rcx
0x1800080cb  jz      loc_180008197
0x1800080d1  mov     edx, [rdx+rdi*8+20h]; unsigned __int64
0x1800080d5  mov     r8, r14; unsigned __int16 *
0x1800080d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800080dd  mov     r11, [rbx+28h]
0x1800080e1  mov     r8, r14; unsigned __int16 *
0x1800080e4  mov     rcx, rbx; this
0x1800080e7  mov     rdx, [r11]
0x1800080ea  mov     rdx, [rdx+rdi*8+28h]; unsigned __int16 *
0x1800080ef  call    ?SendPrinterRenameToClient@CUmRdpPrn@@AEAAHPEBG0@Z; CUmRdpPrn::SendPrinterRenameToClient(ushort const *,ushort const *)
0x1800080f4  test    eax, eax
0x1800080f6  jz      loc_18000818D
0x1800080fc  mov     rcx, gs:60h
0x180008105  mov     r9, r15; dwBytes
0x180008108  mov     rax, [rbx+28h]
0x18000810c  xor     edx, edx; dwFlags
0x18000810e  mov     rcx, [rcx+30h]; hHeap
0x180008112  mov     r8, [rax]
0x180008115  mov     r8, [r8+rdi*8+28h]; lpMem
0x18000811a  call    cs:__imp_HeapReAlloc
0x180008120  mov     rcx, [rbx+28h]
0x180008124  mov     r8, [rcx]
0x180008127  test    rax, rax
0x18000812a  jz      short loc_18000813E
0x18000812c  mov     [r8+rdi*8+28h], rax
0x180008131  mov     rax, [rbx+28h]
0x180008135  mov     rcx, [rax]
0x180008138  mov     [rcx+rdi*8+30h], esi
0x18000813c  jmp     short loc_180008170
0x18000813e  mov     rcx, gs:60h
0x180008147  xor     edx, edx; dwFlags
0x180008149  mov     r8, [r8+rdi*8+28h]; lpMem
0x18000814e  mov     rcx, [rcx+30h]; hHeap
0x180008152  call    cs:__imp_HeapFree
0x180008158  mov     rax, [rbx+28h]
0x18000815c  mov     rcx, [rax]
0x18000815f  mov     [rcx+rdi*8+28h], r12
0x180008164  mov     rax, [rbx+28h]
0x180008168  mov     rcx, [rax]
0x18000816b  mov     [rcx+rdi*8+30h], r12d
0x180008170  mov     rax, [rbx+28h]
0x180008174  mov     rdx, [rax]
0x180008177  mov     rcx, [rdx+rdi*8+28h]; unsigned __int16 *
0x18000817c  test    rcx, rcx
0x18000817f  jz      short loc_18000818D
0x180008181  mov     edx, [rdx+rdi*8+30h]; unsigned __int64
0x180008185  mov     r8, r14; unsigned __int16 *
0x180008188  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000818d  mov     edi, 1
0x180008192  jmp     loc_1800082AF
0x180008197  xor     r8d, r8d; unsigned __int16 **
0x18000819a  lea     rcx, EVENT_NOTIFY_INSUFFICIENTRESOURCES; struct _EVENT_DESCRIPTOR *
0x1800081a1  xor     edx, edx; int
0x1800081a3  call    ?TsLogError@@YAXAEBU_EVENT_DESCRIPTOR@@HQEAPEAGK@Z; TsLogError(_EVENT_DESCRIPTOR const &,int,ushort * * const,ulong)
0x1800081a8  mov     edi, r12d
0x1800081ab  jmp     loc_1800082AF
0x1800081b0  lea     r8, [rbp+pDefault]; pDefault
0x1800081b4  mov     rcx, r14; pPrinterName
0x1800081b7  lea     rdx, [rbp+phPrinter]; phPrinter
0x1800081bb  call    cs:__imp_OpenPrinterW
0x1800081c1  mov     edi, eax
0x1800081c3  test    eax, eax
0x1800081c5  jnz     short loc_1800081F7
0x1800081c7  mov     rax, [rbx]
0x1800081ca  cmp     [rax+878h], r12d
0x1800081d1  jnz     loc_1800082AF
0x1800081d7  call    cs:__imp_GetLastError
0x1800081dd  cmp     eax, 709h
0x1800081e2  jnz     short loc_1800081EC
0x1800081e4  call    cs:__imp_GetLastError
0x1800081ea  jmp     short loc_18000818D
0x1800081ec  call    cs:__imp_GetLastError
0x1800081f2  jmp     loc_1800082AF
0x1800081f7  mov     rdx, [rbp+phPrinter]; void *
0x1800081fb  lea     r8, [rbp+var_28]; unsigned __int16 **
0x1800081ff  mov     rcx, rbx; this
0x180008202  call    ?GetPrinterPortName@CUmRdpPrn@@AEAAHPEAXPEAPEAG@Z; CUmRdpPrn::GetPrinterPortName(void *,ushort * *)
0x180008207  mov     edi, eax
0x180008209  test    eax, eax
0x18000820b  jz      short loc_1800081EC
0x18000820d  mov     r15, [rbx+28h]
0x180008211  lea     r8, [rbp+arg_0]; unsigned int *
0x180008215  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x180008219  mov     rcx, r15; struct tagDRDEVLST *
0x18000821c  call    ?DRDEVLST_FindByServerDeviceName@@YAHPEAUtagDRDEVLST@@PEBGPEAK@Z; DRDEVLST_FindByServerDeviceName(tagDRDEVLST *,ushort const *,ulong *)
0x180008221  test    eax, eax
0x180008223  jz      loc_1800082AF
0x180008229  mov     eax, [rbp+arg_0]
0x18000822c  mov     r8, [r15]
0x18000822f  lea     rcx, [rax+rax*4]
0x180008233  shl     rcx, 4
0x180008237  mov     edx, [rcx+r8+8]
0x18000823c  lea     eax, [rdx-1]
0x18000823f  cmp     eax, 1
0x180008242  jbe     short loc_180008249
0x180008244  cmp     edx, 10h
0x180008247  jnz     short loc_1800082AF
0x180008249  lea     r9, [rcx+34h]
0x18000824d  mov     rdx, r14; unsigned __int16 *
0x180008250  add     r9, r8; char *
0x180008253  mov     rcx, rbx; this
0x180008256  mov     r8, [rbx+0C8h]
0x18000825d  mov     r8, [r8+20h]; unsigned __int16 *
0x180008261  call    ?SendAddPrinterMsgToClient@CUmRdpPrn@@AEAAHPEBG0PEBD@Z; CUmRdpPrn::SendAddPrinterMsgToClient(ushort const *,ushort const *,char const *)
0x180008266  mov     rdx, [rbx]
0x180008269  mov     rcx, [rbp+phPrinter]; void *
0x18000826d  mov     edx, [rdx]; unsigned int
0x18000826f  call    ?AddSessionIDToPrinterQueue@@YAKPEAXK@Z; AddSessionIDToPrinterQueue(void *,ulong)
0x180008274  mov     rcx, [rbx+28h]; struct tagDRDEVLST *
0x180008278  lea     rax, aUnknown; "UNKNOWN"
0x18000827f  mov     [rsp+70h+var_40], rax; char *
0x180008284  mov     r9d, 4; unsigned int
0x18000828a  mov     [rsp+70h+var_48], r14; unsigned __int16 *
0x18000828f  mov     r8d, esi; unsigned int
0x180008292  or      edx, 0FFFFFFFFh; unsigned int
0x180008295  mov     [rsp+70h+var_50], r14; unsigned __int16 *
0x18000829a  call    ?DRDEVLST_Add@@YAHPEAUtagDRDEVLST@@KKKPEBG1PEBD@Z; DRDEVLST_Add(tagDRDEVLST *,ulong,ulong,ulong,ushort const *,ushort const *,char const *)
0x18000829f  mov     edi, eax
0x1800082a1  test    eax, eax
0x1800082a3  jz      short loc_1800082AF
0x1800082a5  mov     edx, esi; unsigned int
0x1800082a7  mov     rcx, rbx; this
0x1800082aa  call    ?RegisterPrinterConfigChangeNotification@CUmRdpPrn@@AEAAHK@Z; CUmRdpPrn::RegisterPrinterConfigChangeNotification(ulong)
0x1800082af  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800082b3  test    rcx, rcx
0x1800082b6  jz      short loc_1800082BE
0x1800082b8  call    cs:__imp_ClosePrinter
0x1800082be  mov     eax, edi
0x1800082c0  lea     r11, [rsp+70h+var_s0]
0x1800082c5  mov     rbx, [r11+38h]
0x1800082c9  mov     rsi, [r11+40h]
0x1800082cd  mov     rsp, r11
0x1800082d0  pop     r15
0x1800082d2  pop     r14
0x1800082d4  pop     r12
0x1800082d6  pop     rdi
0x1800082d7  pop     rbp
0x1800082d8  retn
```

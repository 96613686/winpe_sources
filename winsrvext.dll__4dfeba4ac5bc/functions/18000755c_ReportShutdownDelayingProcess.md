# ReportShutdownDelayingProcess

- ea: `0x18000755c`
- end: `0x180007889`
- name: `ReportShutdownDelayingProcess`
- size: `813`
- prototype: `NTSTATUS __fastcall(__int64, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000592c`
- `0x180009688`

## callees

- `0x180001090`
- `0x180007124`
- `0x18000755c`
- `0x1800138f0`

## import_xrefs

- `ntdll!RtlQueryPackageIdentity` at `0x180007610`
- `ntdll!RtlQueryPackageIdentity` at `0x180007610`
- `ntdll!NtQueryInformationProcess` at `0x1800075b3`
- `ntdll!NtQueryInformationProcess` at `0x1800075b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800075dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800075dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007623`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007623`

## pseudocode

```c
NTSTATUS __fastcall ReportShutdownDelayingProcess(__int64 a1, int a2, int a3)
{
  NTSTATUS result; // eax
  void *v7; // rcx
  BOOL v8; // edi
  __int64 v9; // r8
  int v10; // edi
  __int64 v11; // rbx
  __int64 *v12; // rax
  __int64 v13; // rcx
  int v14; // ecx
  __int64 *v15; // rcx
  __int64 v16; // rax
  const wchar_t *v17; // rax
  __int64 v18; // rcx
  int v19; // ecx
  __int64 v20; // rcx
  __int64 *v21; // rdx
  __int64 v22; // r9
  const wchar_t *v23; // rax
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  int v25; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v28[16]; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+68h] [rbp-98h]
  int v31; // [rsp+6Ch] [rbp-94h]
  __int64 *v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  __int64 *v34; // [rsp+80h] [rbp-80h]
  __int64 v35; // [rsp+88h] [rbp-78h]
  __int64 *v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+98h] [rbp-68h]
  int v38; // [rsp+9Ch] [rbp-64h]
  int *v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  __int64 *v41; // [rsp+B0h] [rbp-50h]
  __int64 v42; // [rsp+B8h] [rbp-48h]
  _WORD v43[128]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE ProcessInformation[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 *v45; // [rsp+1C8h] [rbp+C8h]

  result = NtQueryInformationProcess(*(HANDLE *)(a1 + 80), ProcessImageFileNameWin32, ProcessInformation, 0x218u, 0);
  if ( result >= 0 )
  {
    v7 = *(void **)(a1 + 80);
    TokenHandle = 0;
    v8 = 0;
    result = OpenProcessToken(v7, 8u, &TokenHandle);
    if ( result )
    {
      v24 = 256;
      v10 = ((__int64 (__fastcall *)(void *, _WORD *, __int64 *, _QWORD, _QWORD, _QWORD))RtlQueryPackageIdentity)(
              TokenHandle,
              v43,
              &v24,
              0,
              0,
              0);
      result = CloseHandle(TokenHandle);
      v8 = v10 >= 0;
    }
    v11 = -1;
    if ( (unsigned int)dword_18001D0D8 > 5 )
    {
      result = qword_18001D0E8;
      if ( (qword_18001D0E8 & 0x400000000000LL) != 0 )
      {
        result = 0;
        if ( (qword_18001D0F0 & 0x400000000000LL) == qword_18001D0F0 )
        {
          v27 = 0x1000000;
          v32 = &v27;
          v12 = v45;
          v33 = 8;
          if ( v45 )
          {
            v13 = -1;
            do
              ++v13;
            while ( *((_WORD *)v45 + v13) );
            v14 = 2 * v13 + 2;
          }
          else
          {
            v12 = &qword_180017108;
            v14 = 2;
          }
          LODWORD(v35) = v14;
          v15 = (__int64 *)v43;
          v34 = v12;
          if ( !v8 )
            v15 = &qword_180017108;
          HIDWORD(v35) = 0;
          v16 = -1;
          do
            ++v16;
          while ( *((_WORD *)v15 + v16) );
          v36 = v15;
          v37 = 2 * v16 + 2;
          v38 = 0;
          v40 = 4;
          LODWORD(v24) = a2;
          v42 = 4;
          v39 = &v25;
          v41 = &v24;
          result = tlgWriteTransfer_EventWriteTransfer(&dword_18001D0D8, byte_180018529, 0, 0, 7, v28, v24, a3 != 0);
        }
      }
    }
    if ( v8 )
    {
      if ( (winsrvextEnableBits & 1) == 0 )
        return result;
      v17 = (const wchar_t *)v45;
      LODWORD(v24) = a2;
      if ( v45 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *((_WORD *)v45 + v18) );
        v19 = 2 * v18 + 2;
      }
      else
      {
        v17 = L"NULL";
        v19 = 10;
      }
      v29 = v17;
      v30 = v19;
      v31 = 0;
      do
        ++v11;
      while ( v43[v11] );
      v33 = (unsigned int)(2 * v11 + 2);
      v20 = (__int64)v43;
      v32 = (__int64 *)v43;
      v34 = &v24;
      v21 = WINSRVEXT_PROCESS_DELAYING_SHUTDOWN_WITH_PACKAGE_NAME;
      v35 = 4;
      v22 = 4;
    }
    else
    {
      if ( (winsrvextEnableBits & 1) == 0 )
        return result;
      v23 = (const wchar_t *)v45;
      LODWORD(v24) = a2;
      if ( v45 )
      {
        do
          ++v11;
        while ( *((_WORD *)v45 + v11) );
        v20 = (unsigned int)(2 * v11 + 2);
      }
      else
      {
        v23 = L"NULL";
        v20 = 10;
      }
      v29 = v23;
      v21 = WINSRVEXT_PROCESS_DELAYING_SHUTDOWN;
      v30 = v20;
      v32 = &v24;
      v22 = 3;
      v31 = 0;
      v33 = 4;
    }
    return McGenEventWrite_EventWriteTransfer(v20, v21, v9, v22, v28);
  }
  return result;
}

```

## disassembly

```asm
0x18000755c  mov     [rsp-8+arg_8], rbx
0x180007561  mov     [rsp-8+arg_10], rsi
0x180007566  push    rbp
0x180007567  push    rdi
0x180007568  push    r13
0x18000756a  push    r14
0x18000756c  push    r15
0x18000756e  lea     rbp, [rsp-2F0h]
0x180007576  sub     rsp, 3F0h
0x18000757d  mov     rax, cs:__security_cookie
0x180007584  xor     rax, rsp
0x180007587  mov     [rbp+310h+var_30], rax
0x18000758e  xor     r15d, r15d
0x180007591  mov     r14d, r8d
0x180007594  mov     esi, edx
0x180007596  mov     [rsp+410h+ReturnLength], r15; ReturnLength
0x18000759b  mov     rbx, rcx
0x18000759e  lea     r8, [rbp+310h+ProcessInformation]; ProcessInformation
0x1800075a5  mov     rcx, [rcx+50h]; ProcessHandle
0x1800075a9  mov     r9d, 218h; ProcessInformationLength
0x1800075af  lea     edx, [r15+2Bh]; ProcessInformationClass
0x1800075b3  call    cs:__imp_NtQueryInformationProcess
0x1800075ba  nop     dword ptr [rax+rax+00h]
0x1800075bf  test    eax, eax
0x1800075c1  js      loc_18000785D
0x1800075c7  mov     rcx, [rbx+50h]; ProcessHandle
0x1800075cb  lea     r8, [rsp+410h+TokenHandle]; TokenHandle
0x1800075d0  lea     edx, [r15+8]; DesiredAccess
0x1800075d4  mov     [rsp+410h+TokenHandle], r15
0x1800075d9  mov     edi, r15d
0x1800075dc  call    cs:__imp_OpenProcessToken
0x1800075e3  nop     dword ptr [rax+rax+00h]
0x1800075e8  test    eax, eax
0x1800075ea  jz      short loc_180007634
0x1800075ec  mov     rcx, [rsp+410h+TokenHandle]
0x1800075f1  lea     r8, [rsp+410h+var_3E0]
0x1800075f6  mov     [rsp+410h+var_3E8], r15
0x1800075fb  lea     rdx, [rbp+310h+var_350]
0x1800075ff  xor     r9d, r9d
0x180007602  mov     [rsp+410h+ReturnLength], r15
0x180007607  mov     [rsp+410h+var_3E0], 100h
0x180007610  call    cs:__imp_RtlQueryPackageIdentity
0x180007617  nop     dword ptr [rax+rax+00h]
0x18000761c  mov     rcx, [rsp+410h+TokenHandle]; hObject
0x180007621  mov     edi, eax
0x180007623  call    cs:__imp_CloseHandle
0x18000762a  nop     dword ptr [rax+rax+00h]
0x18000762f  not     edi
0x180007631  shr     edi, 1Fh
0x180007634  mov     ecx, cs:dword_18001D0D8
0x18000763a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000763e  lea     r13d, [rbx+5]
0x180007642  cmp     ecx, 5
0x180007645  jbe     loc_180007752
0x18000764b  mov     rcx, cs:qword_18001D0F0
0x180007652  mov     rdx, 400000000000h
0x18000765c  mov     rax, cs:qword_18001D0E8
0x180007663  test    rdx, rax
0x180007666  jz      loc_180007752
0x18000766c  mov     rax, rcx
0x18000766f  and     rax, rdx
0x180007672  cmp     rax, rcx
0x180007675  jnz     loc_180007752
0x18000767b  lea     rax, [rsp+410h+var_3C8]
0x180007680  mov     [rsp+410h+var_3C8], 1000000h
0x180007689  mov     [rsp+410h+var_3A0], rax
0x18000768e  lea     rdx, qword_180017108
0x180007695  mov     rax, [rbp+310h+var_248]
0x18000769c  mov     [rsp+410h+var_398], 8
0x1800076a5  test    rax, rax
0x1800076a8  jz      short loc_1800076C0
0x1800076aa  mov     rcx, rbx
0x1800076ad  inc     rcx
0x1800076b0  cmp     [rax+rcx*2], r15w
0x1800076b5  jnz     short loc_1800076AD
0x1800076b7  lea     ecx, ds:2[rcx*2]
0x1800076be  jmp     short loc_1800076C8
0x1800076c0  mov     rax, rdx
0x1800076c3  mov     ecx, 2
0x1800076c8  mov     dword ptr [rbp+310h+var_388], ecx
0x1800076cb  test    edi, edi
0x1800076cd  lea     rcx, [rbp+310h+var_350]
0x1800076d1  mov     [rbp+310h+var_390], rax
0x1800076d5  cmovz   rcx, rdx
0x1800076d9  mov     dword ptr [rbp+310h+var_388+4], r15d
0x1800076dd  mov     rax, rbx
0x1800076e0  inc     rax
0x1800076e3  cmp     [rcx+rax*2], r15w
0x1800076e8  jnz     short loc_1800076E0
0x1800076ea  lea     eax, ds:2[rax*2]
0x1800076f1  mov     [rbp+310h+var_380], rcx
0x1800076f5  mov     [rbp+310h+var_378], eax
0x1800076f8  lea     rdx, byte_180018529
0x1800076ff  mov     eax, r15d
0x180007702  mov     [rbp+310h+var_374], r15d
0x180007706  test    r14d, r14d
0x180007709  mov     [rbp+310h+var_368], r13
0x18000770d  lea     rcx, dword_18001D0D8
0x180007714  mov     dword ptr [rsp+410h+var_3E0], esi
0x180007718  setnz   al
0x18000771b  mov     [rbp+310h+var_358], r13
0x18000771f  mov     [rsp+410h+var_3D8], eax
0x180007723  xor     r9d, r9d
0x180007726  lea     rax, [rsp+410h+var_3D8]
0x18000772b  xor     r8d, r8d
0x18000772e  mov     [rbp+310h+var_370], rax
0x180007732  lea     rax, [rsp+410h+var_3E0]
0x180007737  mov     [rbp+310h+var_360], rax
0x18000773b  lea     rax, [rsp+410h+var_3C0]
0x180007740  mov     [rsp+410h+var_3E8], rax
0x180007745  mov     dword ptr [rsp+410h+ReturnLength], 7
0x18000774d  call    _tlgWriteTransfer_EventWriteTransfer
0x180007752  test    edi, edi
0x180007754  jz      loc_1800077EC
0x18000775a  test    cs:winsrvextEnableBits, 1
0x180007761  jz      loc_18000785D
0x180007767  mov     rax, [rbp+310h+var_248]
0x18000776e  mov     dword ptr [rsp+410h+var_3E0], esi
0x180007772  test    rax, rax
0x180007775  jz      short loc_18000778D
0x180007777  mov     rcx, rbx
0x18000777a  inc     rcx
0x18000777d  cmp     [rax+rcx*2], r15w
0x180007782  jnz     short loc_18000777A
0x180007784  lea     ecx, ds:2[rcx*2]
0x18000778b  jmp     short loc_180007799
0x18000778d  lea     rax, aNull; "NULL"
0x180007794  mov     ecx, 0Ah
0x180007799  mov     [rsp+410h+var_3B0], rax
0x18000779e  lea     rax, [rbp+310h+var_350]
0x1800077a2  mov     [rsp+410h+var_3A8], ecx
0x1800077a6  mov     [rsp+410h+var_3A4], r15d
0x1800077ab  inc     rbx
0x1800077ae  cmp     [rax+rbx*2], r15w
0x1800077b3  jnz     short loc_1800077AB
0x1800077b5  lea     eax, ds:2[rbx*2]
0x1800077bc  mov     dword ptr [rsp+410h+var_398+4], r15d
0x1800077c1  mov     dword ptr [rsp+410h+var_398], eax
0x1800077c5  lea     rcx, [rbp+310h+var_350]
0x1800077c9  lea     rax, [rsp+410h+var_3E0]
0x1800077ce  mov     [rsp+410h+var_3A0], rcx
0x1800077d3  mov     [rbp+310h+var_390], rax
0x1800077d7  lea     rdx, WINSRVEXT_PROCESS_DELAYING_SHUTDOWN_WITH_PACKAGE_NAME
0x1800077de  lea     rax, [rsp+410h+var_3C0]
0x1800077e3  mov     [rbp+310h+var_388], r13
0x1800077e7  mov     r9d, r13d
0x1800077ea  jmp     short loc_180007853
0x1800077ec  test    cs:winsrvextEnableBits, 1
0x1800077f3  jz      short loc_18000785D
0x1800077f5  mov     rax, [rbp+310h+var_248]
0x1800077fc  mov     dword ptr [rsp+410h+var_3E0], esi
0x180007800  test    rax, rax
0x180007803  jz      short loc_180007818
0x180007805  inc     rbx
0x180007808  cmp     [rax+rbx*2], r15w
0x18000780d  jnz     short loc_180007805
0x18000780f  lea     ecx, ds:2[rbx*2]
0x180007816  jmp     short loc_180007824
0x180007818  lea     rax, aNull; "NULL"
0x18000781f  mov     ecx, 0Ah
0x180007824  mov     [rsp+410h+var_3B0], rax
0x180007829  lea     rdx, WINSRVEXT_PROCESS_DELAYING_SHUTDOWN
0x180007830  lea     rax, [rsp+410h+var_3E0]
0x180007835  mov     [rsp+410h+var_3A8], ecx
0x180007839  mov     [rsp+410h+var_3A0], rax
0x18000783e  mov     r9d, 3
0x180007844  lea     rax, [rsp+410h+var_3C0]
0x180007849  mov     [rsp+410h+var_3A4], r15d
0x18000784e  mov     [rsp+410h+var_398], r13
0x180007853  mov     [rsp+410h+ReturnLength], rax
0x180007858  call    McGenEventWrite_EventWriteTransfer
0x18000785d  mov     rcx, [rbp+310h+var_30]
0x180007864  xor     rcx, rsp; StackCookie
0x180007867  call    __security_check_cookie
0x18000786c  lea     r11, [rsp+410h+var_20]
0x180007874  mov     rbx, [r11+38h]
0x180007878  mov     rsi, [r11+40h]
0x18000787c  mov     rsp, r11
0x18000787f  pop     r15
0x180007881  pop     r14
0x180007883  pop     r13
0x180007885  pop     rdi
0x180007886  pop     rbp
0x180007887  retn
```

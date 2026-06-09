# NetrEnumerateComputerNames

- ea: `0x18002a1a0`
- end: `0x18002a5f4`
- name: `NetrEnumerateComputerNames`
- size: `1108`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180009010`
- `0x180009090`
- `0x18000a240`
- `0x18000b330`
- `0x18002191c`
- `0x18002a1a0`
- `0x180036191`

## import_xrefs

- `ntdll!RtlGetNtProductType` at `0x18002a250`
- `ntdll!RtlGetNtProductType` at `0x18002a250`
- `api-ms-win-core-kernel32-private-l1-1-0!EnumerateLocalComputerNamesW` at `0x18002a3a8`
- `api-ms-win-core-kernel32-private-l1-1-0!EnumerateLocalComputerNamesW` at `0x18002a3ec`
- `api-ms-win-core-kernel32-private-l1-1-0!EnumerateLocalComputerNamesW` at `0x18002a3a8`
- `api-ms-win-core-kernel32-private-l1-1-0!EnumerateLocalComputerNamesW` at `0x18002a3ec`
- `netutils!NetApiBufferFree` at `0x18002a2a2`
- `netutils!NetApiBufferFree` at `0x18002a2d5`
- `netutils!NetApiBufferFree` at `0x18002a2a2`
- `netutils!NetApiBufferFree` at `0x18002a2d5`
- `netutils!NetApiBufferAllocate` at `0x18002a3ca`
- `netutils!NetApiBufferAllocate` at `0x18002a48c`
- `netutils!NetApiBufferAllocate` at `0x18002a3ca`
- `netutils!NetApiBufferAllocate` at `0x18002a48c`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppCloseLog` at `0x18002a2ea`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppCloseLog` at `0x18002a2ea`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppOpenLog` at `0x18002a21f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppOpenLog` at `0x18002a21f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a240`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a288`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a2c0`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a323`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a350`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a38b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a42a`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a4e9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a51f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a5e3`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a240`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a288`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a2c0`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a323`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a350`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a38b`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a42a`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a4e9`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a51f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a5e3`

## string_xrefs

- `0x18002a237`: `NetrEnumerateComputerNames called: NameType = 0x%lx, Flags = 0x%lx\n`
- `0x18002a281`: `NetrEnumerateComputerNames: Not supported on wksta: %lu\n`
- `0x18002a31c`: `NetrEnumerateComputerNames: Invalid Flags passed\n`
- `0x18002a349`: `NetrEnumerateComputerNames: Invalid name type passed %lu\n`
- `0x18002a384`: `NetrEnumerateComputerNames: WsImpersonateClient failed: 0x%lx\n`
- `0x18002a421`: `NetrEnumerateComputerNames: EnumerateLocalComputerNamesW failed 0x%lx\n`
- `0x18002a40b`: `NetrEnumerateComputerNames: EnumerateLocalComputerNamesW (2) failed 0x%lx\n`
- `0x18002a4e2`: `NetrEnumerateComputerNames: Returning names:`
- `0x18002a5dc`: `NetrEnumerateComputerNames: No names returned\n`
- `0x18002a2b9`: `NetrEnumerateComputerNames: Failed 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrEnumerateComputerNames(__int64 a1, unsigned int a2, unsigned int a3, LPVOID *a4)
{
  __int64 result; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  enum _NT_PRODUCT_TYPE v12; // eax
  DWORD v13; // ebx
  LPVOID v14; // rcx
  LPVOID v15; // rcx
  __int64 v16; // rcx
  DWORD v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  _WORD *v20; // rdx
  DWORD v21; // r8d
  __int64 v22; // rdi
  __int64 v23; // rax
  __int64 v24; // rax
  char *v25; // rax
  __int64 v26; // rcx
  _DWORD *v27; // rax
  __int64 v28; // rcx
  unsigned int i; // edi
  char *v30; // r14
  char *v31; // rdi
  _WORD *v32; // rbx
  int v33; // r15d
  __int64 v34; // rax
  unsigned __int16 v35; // ax
  __int64 v36; // rax
  __int64 v37; // rax
  int v38; // [rsp+40h] [rbp-28h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+44h] [rbp-24h] BYREF
  LPVOID Buffer; // [rsp+48h] [rbp-20h] BYREF
  LPVOID Src; // [rsp+50h] [rbp-18h] BYREF

  ProductType = 0;
  v38 = 0;
  Src = 0;
  Buffer = 0;
  result = WsValidateRpcProtSeq(0);
  if ( (_DWORD)result )
    return result;
  if ( (unsigned int)NetpAccessCheckAndAuditEx(&WsNetApiMapping, v8, L"NetAPI") )
    return 5;
  if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v9) )
    NetSetuppOpenLog();
  if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v10) )
    NetpLogPrintHelper(L"NetrEnumerateComputerNames called: NameType = 0x%lx, Flags = 0x%lx\n", a2, a3);
  if ( RtlGetNtProductType(&ProductType) )
  {
    v12 = ProductType;
  }
  else
  {
    v12 = NtProductWinNt;
    ProductType = NtProductWinNt;
  }
  if ( (unsigned int)(v12 - 2) > 1 )
  {
    if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v11) )
      NetpLogPrintHelper(L"NetrEnumerateComputerNames: Not supported on wksta: %lu\n", (unsigned int)ProductType);
    v13 = 50;
    goto LABEL_15;
  }
  if ( a3 && (a3 & 1) == 0 )
  {
    if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v11) )
      NetpLogPrintHelper(L"NetrEnumerateComputerNames: Invalid Flags passed\n");
    v13 = 1004;
    goto LABEL_15;
  }
  if ( (int)a2 >= 3 )
  {
    if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v11) )
      NetpLogPrintHelper(L"NetrEnumerateComputerNames: Invalid name type passed %lu\n", a2);
    v13 = 87;
    goto LABEL_15;
  }
  v13 = WsImpersonateClient2(0, 0);
  if ( v13 )
  {
    if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v16) )
      NetpLogPrintHelper(L"NetrEnumerateComputerNames: WsImpersonateClient failed: 0x%lx\n", v13);
    goto LABEL_15;
  }
  v17 = EnumerateLocalComputerNamesW(a2, 0, Src, &v38);
  v13 = v17;
  if ( !v17 )
  {
LABEL_40:
    v13 = EnumerateLocalComputerNamesW(a2, 0, Src, &v38);
    if ( v13 )
    {
      if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v19) )
        NetpLogPrintHelper(L"NetrEnumerateComputerNames: EnumerateLocalComputerNamesW (2) failed 0x%lx\n", v13);
    }
    else
    {
      v20 = Src;
      v21 = 16;
      v38 = 16;
      v22 = 0;
      while ( *v20 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v20[v23] );
        v22 = (unsigned int)(v22 + 1);
        v21 += 2 * (v23 + 9);
        v24 = -1;
        v38 = v21;
        do
          ++v24;
        while ( v20[v24] );
        v20 += (unsigned int)(v24 + 1);
      }
      v13 = NetApiBufferAllocate(v21, &Buffer);
      if ( !v13 )
      {
        *(_DWORD *)Buffer = v22;
        v25 = (char *)Buffer;
        if ( (_DWORD)v22 )
        {
          v30 = (char *)Buffer + 16;
          *((_QWORD *)Buffer + 1) = (char *)Buffer + 16;
          v31 = &v25[16 * v22 + 16];
          v32 = Src;
          v33 = 0;
          while ( *v32 )
          {
            v34 = -1;
            *(_QWORD *)&v30[16 * v33 + 8] = v31;
            do
              ++v34;
            while ( v32[v34] );
            v35 = 2 * v34;
            *(_WORD *)&v30[16 * v33] = v35;
            v35 += 2;
            *(_WORD *)&v30[16 * v33 + 2] = v35;
            memcpy_0(v31, v32, v35);
            v36 = *(unsigned __int16 *)&v30[16 * v33++ + 2];
            v31 += v36;
            v37 = -1;
            do
              ++v37;
            while ( v32[v37] );
            v32 += (unsigned int)(v37 + 1);
          }
        }
        else
        {
          *((_QWORD *)Buffer + 1) = 0;
        }
        v13 = 0;
      }
    }
    goto LABEL_57;
  }
  if ( v17 == 234 )
  {
    v13 = NetApiBufferAllocate(2 * v38, &Src);
    if ( v13 )
      goto LABEL_57;
    goto LABEL_40;
  }
  if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v18) )
    NetpLogPrintHelper(L"NetrEnumerateComputerNames: EnumerateLocalComputerNamesW failed 0x%lx\n", v13);
LABEL_57:
  WsRevertToSelf2(0, 0);
  if ( !v13 )
  {
    v27 = Buffer;
    *a4 = Buffer;
    if ( *v27 )
    {
      if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v26) )
        NetpLogPrintHelper(L"NetrEnumerateComputerNames: Returning names:");
      for ( i = 0; i < *(_DWORD *)Buffer; ++i )
      {
        if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v28) )
          NetpLogPrintHelper(L" %wZ", *((_QWORD *)Buffer + 1) + 16LL * i);
      }
      if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v28) )
        NetpLogPrintHelper(L"\n");
    }
    else if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v26) )
    {
      NetpLogPrintHelper(L"NetrEnumerateComputerNames: No names returned\n");
    }
    goto LABEL_19;
  }
LABEL_15:
  v14 = Buffer;
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v14) )
    NetpLogPrintHelper(L"NetrEnumerateComputerNames: Failed 0x%lx\n", v13);
LABEL_19:
  v15 = Src;
  if ( Src )
    NetApiBufferFree(Src);
  if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v15) )
    NetSetuppCloseLog();
  return v13;
}

```

## disassembly

```asm
0x18002a1a0  push    rbp
0x18002a1a2  push    rbx
0x18002a1a3  push    rsi
0x18002a1a4  push    rdi
0x18002a1a5  push    r12
0x18002a1a7  push    r13
0x18002a1a9  push    r14
0x18002a1ab  push    r15
0x18002a1ad  mov     rbp, rsp
0x18002a1b0  sub     rsp, 68h
0x18002a1b4  xor     r13d, r13d
0x18002a1b7  xor     ecx, ecx
0x18002a1b9  mov     [rbp+ProductType], r13d
0x18002a1bd  mov     r12, r9
0x18002a1c0  mov     [rbp+var_28], r13d
0x18002a1c4  mov     ebx, r8d
0x18002a1c7  mov     [rbp+Src], r13
0x18002a1cb  mov     edi, edx
0x18002a1cd  mov     [rbp+Buffer], r13
0x18002a1d1  call    WsValidateRpcProtSeq
0x18002a1d6  test    eax, eax
0x18002a1d8  jnz     loc_18002A2F8
0x18002a1de  mov     rax, cs:NetApiSd
0x18002a1e5  lea     rcx, WsNetApiMapping
0x18002a1ec  mov     [rsp+68h+var_38], rcx
0x18002a1f1  lea     esi, [r13+1]
0x18002a1f5  mov     [rsp+68h+var_40], esi
0x18002a1f9  lea     r8, aNetapi; "NetAPI"
0x18002a200  mov     [rsp+68h+var_48], rax
0x18002a205  call    NetpAccessCheckAndAuditEx
0x18002a20a  test    eax, eax
0x18002a20c  jz      short loc_18002A216
0x18002a20e  lea     eax, [rsi+4]
0x18002a211  jmp     loc_18002A2F8
0x18002a216  call    IsNetpManageIPCConnectPresent
0x18002a21b  test    al, al
0x18002a21d  jz      short loc_18002A22B
0x18002a21f  call    cs:__imp_NetSetuppOpenLog
0x18002a226  nop     dword ptr [rax+rax+00h]
0x18002a22b  call    IsNetpManageIPCConnectPresent
0x18002a230  test    al, al
0x18002a232  jz      short loc_18002A24C
0x18002a234  mov     r8d, ebx
0x18002a237  lea     rcx, aNetrenumeratec_8; "NetrEnumerateComputerNames called: Name"...
0x18002a23e  mov     edx, edi
0x18002a240  call    cs:__imp_NetpLogPrintHelper
0x18002a247  nop     dword ptr [rax+rax+00h]
0x18002a24c  lea     rcx, [rbp+ProductType]; ProductType
0x18002a250  call    cs:__imp_RtlGetNtProductType
0x18002a257  nop     dword ptr [rax+rax+00h]
0x18002a25c  test    al, al
0x18002a25e  jnz     short loc_18002A267
0x18002a260  mov     eax, esi
0x18002a262  mov     [rbp+ProductType], eax
0x18002a265  jmp     short loc_18002A26A
0x18002a267  mov     eax, [rbp+ProductType]
0x18002a26a  add     eax, 0FFFFFFFEh
0x18002a26d  cmp     eax, esi
0x18002a26f  jbe     loc_18002A30A
0x18002a275  call    IsNetpManageIPCConnectPresent
0x18002a27a  test    al, al
0x18002a27c  jz      short loc_18002A294
0x18002a27e  mov     edx, [rbp+ProductType]
0x18002a281  lea     rcx, aNetrenumeratec_4; "NetrEnumerateComputerNames: Not support"...
0x18002a288  call    cs:__imp_NetpLogPrintHelper
0x18002a28f  nop     dword ptr [rax+rax+00h]
0x18002a294  mov     ebx, 32h ; '2'
0x18002a299  mov     rcx, [rbp+Buffer]; Buffer
0x18002a29d  test    rcx, rcx
0x18002a2a0  jz      short loc_18002A2AE
0x18002a2a2  call    cs:__imp_NetApiBufferFree
0x18002a2a9  nop     dword ptr [rax+rax+00h]
0x18002a2ae  call    IsNetpManageIPCConnectPresent
0x18002a2b3  test    al, al
0x18002a2b5  jz      short loc_18002A2CC
0x18002a2b7  mov     edx, ebx
0x18002a2b9  lea     rcx, aNetrenumeratec_0; "NetrEnumerateComputerNames: Failed 0x%l"...
0x18002a2c0  call    cs:__imp_NetpLogPrintHelper
0x18002a2c7  nop     dword ptr [rax+rax+00h]
0x18002a2cc  mov     rcx, [rbp+Src]; Buffer
0x18002a2d0  test    rcx, rcx
0x18002a2d3  jz      short loc_18002A2E1
0x18002a2d5  call    cs:__imp_NetApiBufferFree
0x18002a2dc  nop     dword ptr [rax+rax+00h]
0x18002a2e1  call    IsNetpManageIPCConnectPresent
0x18002a2e6  test    al, al
0x18002a2e8  jz      short loc_18002A2F6
0x18002a2ea  call    cs:__imp_NetSetuppCloseLog
0x18002a2f1  nop     dword ptr [rax+rax+00h]
0x18002a2f6  mov     eax, ebx
0x18002a2f8  add     rsp, 68h
0x18002a2fc  pop     r15
0x18002a2fe  pop     r14
0x18002a300  pop     r13
0x18002a302  pop     r12
0x18002a304  pop     rdi
0x18002a305  pop     rsi
0x18002a306  pop     rbx
0x18002a307  pop     rbp
0x18002a308  retn
0x18002a30a  test    ebx, ebx
0x18002a30c  jz      short loc_18002A339
0x18002a30e  test    sil, bl
0x18002a311  jnz     short loc_18002A339
0x18002a313  call    IsNetpManageIPCConnectPresent
0x18002a318  test    al, al
0x18002a31a  jz      short loc_18002A32F
0x18002a31c  lea     rcx, aNetrenumeratec_2; "NetrEnumerateComputerNames: Invalid Fla"...
0x18002a323  call    cs:__imp_NetpLogPrintHelper
0x18002a32a  nop     dword ptr [rax+rax+00h]
0x18002a32f  mov     ebx, 3ECh
0x18002a334  jmp     loc_18002A299
0x18002a339  cmp     edi, 3
0x18002a33c  jl      short loc_18002A366
0x18002a33e  call    IsNetpManageIPCConnectPresent
0x18002a343  test    al, al
0x18002a345  jz      short loc_18002A35C
0x18002a347  mov     edx, edi
0x18002a349  lea     rcx, aNetrenumeratec_3; "NetrEnumerateComputerNames: Invalid nam"...
0x18002a350  call    cs:__imp_NetpLogPrintHelper
0x18002a357  nop     dword ptr [rax+rax+00h]
0x18002a35c  mov     ebx, 57h ; 'W'
0x18002a361  jmp     loc_18002A299
0x18002a366  xor     edx, edx
0x18002a368  xor     ecx, ecx
0x18002a36a  call    WsImpersonateClient2
0x18002a36f  mov     ebx, eax
0x18002a371  test    eax, eax
0x18002a373  jz      short loc_18002A39C
0x18002a375  call    IsNetpManageIPCConnectPresent
0x18002a37a  test    al, al
0x18002a37c  jz      loc_18002A299
0x18002a382  mov     edx, ebx
0x18002a384  lea     rcx, aNetrenumeratec_6; "NetrEnumerateComputerNames: WsImpersona"...
0x18002a38b  call    cs:__imp_NetpLogPrintHelper
0x18002a392  nop     dword ptr [rax+rax+00h]
0x18002a397  jmp     loc_18002A299
0x18002a39c  mov     r8, [rbp+Src]
0x18002a3a0  lea     r9, [rbp+var_28]
0x18002a3a4  xor     edx, edx
0x18002a3a6  mov     ecx, edi
0x18002a3a8  call    cs:__imp_EnumerateLocalComputerNamesW
0x18002a3af  nop     dword ptr [rax+rax+00h]
0x18002a3b4  mov     ebx, eax
0x18002a3b6  test    eax, eax
0x18002a3b8  jz      short loc_18002A3E0
0x18002a3ba  cmp     eax, 0EAh
0x18002a3bf  jnz     short loc_18002A414
0x18002a3c1  mov     ecx, [rbp+var_28]
0x18002a3c4  lea     rdx, [rbp+Src]; Buffer
0x18002a3c8  add     ecx, ecx; ByteCount
0x18002a3ca  call    cs:__imp_NetApiBufferAllocate
0x18002a3d1  nop     dword ptr [rax+rax+00h]
0x18002a3d6  mov     ebx, eax
0x18002a3d8  test    eax, eax
0x18002a3da  jnz     loc_18002A4B7
0x18002a3e0  mov     r8, [rbp+Src]
0x18002a3e4  lea     r9, [rbp+var_28]
0x18002a3e8  xor     edx, edx
0x18002a3ea  mov     ecx, edi
0x18002a3ec  call    cs:__imp_EnumerateLocalComputerNamesW
0x18002a3f3  nop     dword ptr [rax+rax+00h]
0x18002a3f8  mov     ebx, eax
0x18002a3fa  test    eax, eax
0x18002a3fc  jz      short loc_18002A438
0x18002a3fe  call    IsNetpManageIPCConnectPresent
0x18002a403  test    al, al
0x18002a405  jz      loc_18002A4B7
0x18002a40b  lea     rcx, aNetrenumeratec; "NetrEnumerateComputerNames: EnumerateLo"...
0x18002a412  jmp     short loc_18002A428
0x18002a414  call    IsNetpManageIPCConnectPresent
0x18002a419  test    al, al
0x18002a41b  jz      loc_18002A4B7
0x18002a421  lea     rcx, aNetrenumeratec_5; "NetrEnumerateComputerNames: EnumerateLo"...
0x18002a428  mov     edx, ebx
0x18002a42a  call    cs:__imp_NetpLogPrintHelper
0x18002a431  nop     dword ptr [rax+rax+00h]
0x18002a436  jmp     short loc_18002A4B7
0x18002a438  mov     rdx, [rbp+Src]
0x18002a43c  mov     r8d, 10h
0x18002a442  mov     [rbp+var_28], r8d
0x18002a446  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002a44a  mov     edi, r13d
0x18002a44d  mov     ecx, r8d
0x18002a450  cmp     [rdx], r13w
0x18002a454  jz      short loc_18002A485
0x18002a456  mov     rax, r9
0x18002a459  inc     rax
0x18002a45c  cmp     [rdx+rax*2], r13w
0x18002a461  jnz     short loc_18002A459
0x18002a463  lea     eax, [rax+9]
0x18002a466  add     edi, esi
0x18002a468  lea     r8d, [rcx+rax*2]
0x18002a46c  mov     rax, r9
0x18002a46f  mov     [rbp+var_28], r8d
0x18002a473  inc     rax
0x18002a476  cmp     [rdx+rax*2], r13w
0x18002a47b  jnz     short loc_18002A473
0x18002a47d  inc     eax
0x18002a47f  lea     rdx, [rdx+rax*2]
0x18002a483  jmp     short loc_18002A44D
0x18002a485  lea     rdx, [rbp+Buffer]; Buffer
0x18002a489  mov     ecx, r8d; ByteCount
0x18002a48c  call    cs:__imp_NetApiBufferAllocate
0x18002a493  nop     dword ptr [rax+rax+00h]
0x18002a498  mov     ebx, eax
0x18002a49a  test    eax, eax
0x18002a49c  jnz     short loc_18002A4B7
0x18002a49e  mov     rax, [rbp+Buffer]
0x18002a4a2  mov     [rax], edi
0x18002a4a4  mov     rax, [rbp+Buffer]
0x18002a4a8  test    edi, edi
0x18002a4aa  jnz     loc_18002A54E
0x18002a4b0  mov     [rax+8], r13
0x18002a4b4  mov     ebx, r13d
0x18002a4b7  xor     edx, edx
0x18002a4b9  xor     ecx, ecx
0x18002a4bb  call    WsRevertToSelf2
0x18002a4c0  test    ebx, ebx
0x18002a4c2  jnz     loc_18002A299
0x18002a4c8  mov     rax, [rbp+Buffer]
0x18002a4cc  mov     [r12], rax
0x18002a4d0  cmp     [rax], r13d
0x18002a4d3  jbe     loc_18002A5CF
0x18002a4d9  call    IsNetpManageIPCConnectPresent
0x18002a4de  test    al, al
0x18002a4e0  jz      short loc_18002A4F5
0x18002a4e2  lea     rcx, aNetrenumeratec_1; "NetrEnumerateComputerNames: Returning n"...
0x18002a4e9  call    cs:__imp_NetpLogPrintHelper
0x18002a4f0  nop     dword ptr [rax+rax+00h]
0x18002a4f5  mov     rax, [rbp+Buffer]
0x18002a4f9  mov     edi, r13d
0x18002a4fc  cmp     [rax], r13d
0x18002a4ff  jbe     short loc_18002A535
0x18002a501  call    IsNetpManageIPCConnectPresent
0x18002a506  test    al, al
0x18002a508  jz      short loc_18002A52B
0x18002a50a  mov     rax, [rbp+Buffer]
0x18002a50e  lea     rcx, aWz; " %wZ"
0x18002a515  mov     edx, edi
0x18002a517  shl     rdx, 4
0x18002a51b  add     rdx, [rax+8]
0x18002a51f  call    cs:__imp_NetpLogPrintHelper
0x18002a526  nop     dword ptr [rax+rax+00h]
0x18002a52b  mov     rax, [rbp+Buffer]
0x18002a52f  add     edi, esi
0x18002a531  cmp     edi, [rax]
0x18002a533  jb      short loc_18002A501
0x18002a535  call    IsNetpManageIPCConnectPresent
0x18002a53a  test    al, al
0x18002a53c  jz      loc_18002A2CC
0x18002a542  lea     rcx, asc_18004378C; "\n"
0x18002a549  jmp     loc_18002A5E3
0x18002a54e  lea     r14, [rax+10h]
0x18002a552  shl     rdi, 4
0x18002a556  mov     [rax+8], r14
0x18002a55a  add     rdi, r14
0x18002a55d  mov     rbx, [rbp+Src]
0x18002a561  mov     r15d, r13d
0x18002a564  cmp     [rbx], r13w
0x18002a568  jz      loc_18002A4B4
0x18002a56e  mov     esi, r15d
0x18002a571  add     rsi, rsi
0x18002a574  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a578  mov     [r14+rsi*8+8], rdi
0x18002a57d  inc     rax
0x18002a580  cmp     [rbx+rax*2], r13w
0x18002a585  jnz     short loc_18002A57D
0x18002a587  add     ax, ax
0x18002a58a  mov     rdx, rbx; Src
0x18002a58d  mov     [r14+rsi*8], ax
0x18002a592  mov     rcx, rdi; void *
0x18002a595  add     ax, 2
0x18002a599  movzx   r8d, ax; Size
0x18002a59d  mov     [r14+rsi*8+2], r8w
0x18002a5a3  call    memcpy_0
0x18002a5a8  movzx   eax, word ptr [r14+rsi*8+2]
0x18002a5ae  mov     esi, 1
0x18002a5b3  add     r15d, esi
0x18002a5b6  add     rdi, rax
0x18002a5b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a5bd  inc     rax
0x18002a5c0  cmp     [rbx+rax*2], r13w
0x18002a5c5  jnz     short loc_18002A5BD
0x18002a5c7  inc     eax
0x18002a5c9  lea     rbx, [rbx+rax*2]
0x18002a5cd  jmp     short loc_18002A564
0x18002a5cf  call    IsNetpManageIPCConnectPresent
0x18002a5d4  test    al, al
0x18002a5d6  jz      loc_18002A2CC
0x18002a5dc  lea     rcx, aNetrenumeratec_7; "NetrEnumerateComputerNames: No names re"...
0x18002a5e3  call    cs:__imp_NetpLogPrintHelper
0x18002a5ea  nop     dword ptr [rax+rax+00h]
0x18002a5ef  jmp     loc_18002A2CC
```

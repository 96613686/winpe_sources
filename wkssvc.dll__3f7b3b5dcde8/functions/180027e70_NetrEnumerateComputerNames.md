# NetrEnumerateComputerNames

- ea: `0x180027e70`
- end: `0x18002824a`
- name: `NetrEnumerateComputerNames`
- size: `986`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, LPVOID *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008950`
- `0x1800089d0`
- `0x180009a40`
- `0x18000a0c0`
- `0x18002016c`
- `0x180027e70`
- `0x180033159`

## import_xrefs

- `ntdll!RtlGetNtProductType` at `0x180027f14`
- `ntdll!RtlGetNtProductType` at `0x180027f14`
- `api-ms-win-core-kernel32-private-l1-1-0!EnumerateLocalComputerNamesW` at `0x18002802e`
- `api-ms-win-core-kernel32-private-l1-1-0!EnumerateLocalComputerNamesW` at `0x180028066`
- `api-ms-win-core-kernel32-private-l1-1-0!EnumerateLocalComputerNamesW` at `0x18002802e`
- `api-ms-win-core-kernel32-private-l1-1-0!EnumerateLocalComputerNamesW` at `0x180028066`
- `netutils!NetApiBufferFree` at `0x180027f56`
- `netutils!NetApiBufferFree` at `0x180027f7d`
- `netutils!NetApiBufferFree` at `0x180027f56`
- `netutils!NetApiBufferFree` at `0x180027f7d`
- `netutils!NetApiBufferAllocate` at `0x18002804a`
- `netutils!NetApiBufferAllocate` at `0x1800280fa`
- `netutils!NetApiBufferAllocate` at `0x18002804a`
- `netutils!NetApiBufferAllocate` at `0x1800280fa`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppCloseLog` at `0x180027f8c`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppCloseLog` at `0x180027f8c`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppOpenLog` at `0x180027eef`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetSetuppOpenLog` at `0x180027eef`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027f0a`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027f42`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027f6e`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027fbe`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027fe2`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028017`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002809e`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028151`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028181`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002823f`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027f0a`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027f42`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027f6e`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027fbe`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027fe2`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028017`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002809e`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028151`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028181`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002823f`

## string_xrefs

- `0x180027f01`: `NetrEnumerateComputerNames called: NameType = 0x%lx, Flags = 0x%lx\n`
- `0x180027f3b`: `NetrEnumerateComputerNames: Not supported on wksta: %lu\n`
- `0x180027fb7`: `NetrEnumerateComputerNames: Invalid Flags passed\n`
- `0x180027fdb`: `NetrEnumerateComputerNames: Invalid name type passed %lu\n`
- `0x180028010`: `NetrEnumerateComputerNames: WsImpersonateClient failed: 0x%lx\n`
- `0x180028095`: `NetrEnumerateComputerNames: EnumerateLocalComputerNamesW failed 0x%lx\n`
- `0x18002807f`: `NetrEnumerateComputerNames: EnumerateLocalComputerNamesW (2) failed 0x%lx\n`
- `0x18002814a`: `NetrEnumerateComputerNames: Returning names:`
- `0x180028238`: `NetrEnumerateComputerNames: No names returned\n`
- `0x180027f67`: `NetrEnumerateComputerNames: Failed 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrEnumerateComputerNames(__int64 a1, unsigned int a2, unsigned int a3, LPVOID *a4)
{
  __int64 result; // rax
  __int64 v8; // rdx
  enum _NT_PRODUCT_TYPE v9; // eax
  DWORD v10; // ebx
  DWORD v11; // eax
  _WORD *v12; // rdx
  DWORD v13; // r8d
  __int64 v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rax
  char *v17; // rax
  _DWORD *v18; // rax
  unsigned int i; // edi
  char *v20; // r14
  char *v21; // rdi
  _WORD *v22; // rbx
  int v23; // r15d
  __int64 v24; // rax
  unsigned __int16 v25; // ax
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // [rsp+40h] [rbp-28h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+44h] [rbp-24h] BYREF
  LPVOID Buffer; // [rsp+48h] [rbp-20h] BYREF
  LPVOID Src; // [rsp+50h] [rbp-18h] BYREF

  ProductType = 0;
  v28 = 0;
  Src = 0;
  Buffer = 0;
  result = WsValidateRpcProtSeq(0);
  if ( (_DWORD)result )
    return result;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsNetApiMapping, v8, L"NetAPI") )
    return 5;
  if ( IsNetpManageIPCConnectPresent() )
    NetSetuppOpenLog();
  if ( IsNetpManageIPCConnectPresent() )
    NetpLogPrintHelper(L"NetrEnumerateComputerNames called: NameType = 0x%lx, Flags = 0x%lx\n", a2, a3);
  if ( RtlGetNtProductType(&ProductType) )
  {
    v9 = ProductType;
  }
  else
  {
    v9 = NtProductWinNt;
    ProductType = NtProductWinNt;
  }
  if ( (unsigned int)(v9 - 2) > 1 )
  {
    if ( IsNetpManageIPCConnectPresent() )
      NetpLogPrintHelper(L"NetrEnumerateComputerNames: Not supported on wksta: %lu\n", (unsigned int)ProductType);
    v10 = 50;
    goto LABEL_15;
  }
  if ( a3 && (a3 & 1) == 0 )
  {
    if ( IsNetpManageIPCConnectPresent() )
      NetpLogPrintHelper(L"NetrEnumerateComputerNames: Invalid Flags passed\n");
    v10 = 1004;
    goto LABEL_15;
  }
  if ( (int)a2 >= 3 )
  {
    if ( IsNetpManageIPCConnectPresent() )
      NetpLogPrintHelper(L"NetrEnumerateComputerNames: Invalid name type passed %lu\n", a2);
    v10 = 87;
    goto LABEL_15;
  }
  v10 = WsImpersonateClient2(0, 0);
  if ( v10 )
  {
    if ( IsNetpManageIPCConnectPresent() )
      NetpLogPrintHelper(L"NetrEnumerateComputerNames: WsImpersonateClient failed: 0x%lx\n", v10);
    goto LABEL_15;
  }
  v11 = EnumerateLocalComputerNamesW(a2, 0, Src, &v28);
  v10 = v11;
  if ( !v11 )
  {
LABEL_40:
    v10 = EnumerateLocalComputerNamesW(a2, 0, Src, &v28);
    if ( v10 )
    {
      if ( IsNetpManageIPCConnectPresent() )
        NetpLogPrintHelper(L"NetrEnumerateComputerNames: EnumerateLocalComputerNamesW (2) failed 0x%lx\n", v10);
    }
    else
    {
      v12 = Src;
      v13 = 16;
      v28 = 16;
      v14 = 0;
      while ( *v12 )
      {
        v15 = -1;
        do
          ++v15;
        while ( v12[v15] );
        v14 = (unsigned int)(v14 + 1);
        v13 += 2 * (v15 + 9);
        v16 = -1;
        v28 = v13;
        do
          ++v16;
        while ( v12[v16] );
        v12 += (unsigned int)(v16 + 1);
      }
      v10 = NetApiBufferAllocate(v13, &Buffer);
      if ( !v10 )
      {
        *(_DWORD *)Buffer = v14;
        v17 = (char *)Buffer;
        if ( (_DWORD)v14 )
        {
          v20 = (char *)Buffer + 16;
          *((_QWORD *)Buffer + 1) = (char *)Buffer + 16;
          v21 = &v17[16 * v14 + 16];
          v22 = Src;
          v23 = 0;
          while ( *v22 )
          {
            v24 = -1;
            *(_QWORD *)&v20[16 * v23 + 8] = v21;
            do
              ++v24;
            while ( v22[v24] );
            v25 = 2 * v24;
            *(_WORD *)&v20[16 * v23] = v25;
            v25 += 2;
            *(_WORD *)&v20[16 * v23 + 2] = v25;
            memcpy_0(v21, v22, v25);
            v26 = *(unsigned __int16 *)&v20[16 * v23++ + 2];
            v21 += v26;
            v27 = -1;
            do
              ++v27;
            while ( v22[v27] );
            v22 += (unsigned int)(v27 + 1);
          }
        }
        else
        {
          *((_QWORD *)Buffer + 1) = 0;
        }
        v10 = 0;
      }
    }
    goto LABEL_57;
  }
  if ( v11 == 234 )
  {
    v10 = NetApiBufferAllocate(2 * v28, &Src);
    if ( v10 )
      goto LABEL_57;
    goto LABEL_40;
  }
  if ( IsNetpManageIPCConnectPresent() )
    NetpLogPrintHelper(L"NetrEnumerateComputerNames: EnumerateLocalComputerNamesW failed 0x%lx\n", v10);
LABEL_57:
  WsRevertToSelf2(0, 0);
  if ( !v10 )
  {
    v18 = Buffer;
    *a4 = Buffer;
    if ( *v18 )
    {
      if ( IsNetpManageIPCConnectPresent() )
        NetpLogPrintHelper(L"NetrEnumerateComputerNames: Returning names:");
      for ( i = 0; i < *(_DWORD *)Buffer; ++i )
      {
        if ( IsNetpManageIPCConnectPresent() )
          NetpLogPrintHelper(L" %wZ", *((_QWORD *)Buffer + 1) + 16LL * i);
      }
      if ( IsNetpManageIPCConnectPresent() )
        NetpLogPrintHelper(L"\n");
    }
    else if ( IsNetpManageIPCConnectPresent() )
    {
      NetpLogPrintHelper(L"NetrEnumerateComputerNames: No names returned\n");
    }
    goto LABEL_19;
  }
LABEL_15:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( IsNetpManageIPCConnectPresent() )
    NetpLogPrintHelper(L"NetrEnumerateComputerNames: Failed 0x%lx\n", v10);
LABEL_19:
  if ( Src )
    NetApiBufferFree(Src);
  if ( IsNetpManageIPCConnectPresent() )
    NetSetuppCloseLog();
  return v10;
}

```

## disassembly

```asm
0x180027e70  push    rbp
0x180027e72  push    rbx
0x180027e73  push    rsi
0x180027e74  push    rdi
0x180027e75  push    r12
0x180027e77  push    r13
0x180027e79  push    r14
0x180027e7b  push    r15
0x180027e7d  mov     rbp, rsp
0x180027e80  sub     rsp, 68h
0x180027e84  xor     r13d, r13d
0x180027e87  xor     ecx, ecx
0x180027e89  mov     [rbp+ProductType], r13d
0x180027e8d  mov     r12, r9
0x180027e90  mov     [rbp+var_28], r13d
0x180027e94  mov     ebx, r8d
0x180027e97  mov     [rbp+Src], r13
0x180027e9b  mov     edi, edx
0x180027e9d  mov     [rbp+Buffer], r13
0x180027ea1  call    WsValidateRpcProtSeq
0x180027ea6  test    eax, eax
0x180027ea8  jnz     loc_180027F94
0x180027eae  mov     rax, cs:NetApiSd
0x180027eb5  lea     rcx, WsNetApiMapping
0x180027ebc  mov     [rsp+68h+var_38], rcx
0x180027ec1  lea     esi, [r13+1]
0x180027ec5  mov     [rsp+68h+var_40], esi
0x180027ec9  lea     r8, aNetapi; "NetAPI"
0x180027ed0  mov     [rsp+68h+var_48], rax
0x180027ed5  call    NetpAccessCheckAndAuditEx
0x180027eda  test    eax, eax
0x180027edc  jz      short loc_180027EE6
0x180027ede  lea     eax, [rsi+4]
0x180027ee1  jmp     loc_180027F94
0x180027ee6  call    IsNetpManageIPCConnectPresent
0x180027eeb  test    al, al
0x180027eed  jz      short loc_180027EF5
0x180027eef  call    cs:__imp_NetSetuppOpenLog
0x180027ef5  call    IsNetpManageIPCConnectPresent
0x180027efa  test    al, al
0x180027efc  jz      short loc_180027F10
0x180027efe  mov     r8d, ebx
0x180027f01  lea     rcx, aNetrenumeratec_8; "NetrEnumerateComputerNames called: Name"...
0x180027f08  mov     edx, edi
0x180027f0a  call    cs:__imp_NetpLogPrintHelper
0x180027f10  lea     rcx, [rbp+ProductType]; ProductType
0x180027f14  call    cs:__imp_RtlGetNtProductType
0x180027f1a  test    al, al
0x180027f1c  jnz     short loc_180027F25
0x180027f1e  mov     eax, esi
0x180027f20  mov     [rbp+ProductType], eax
0x180027f23  jmp     short loc_180027F28
0x180027f25  mov     eax, [rbp+ProductType]
0x180027f28  add     eax, 0FFFFFFFEh
0x180027f2b  cmp     eax, esi
0x180027f2d  jbe     short loc_180027FA5
0x180027f2f  call    IsNetpManageIPCConnectPresent
0x180027f34  test    al, al
0x180027f36  jz      short loc_180027F48
0x180027f38  mov     edx, [rbp+ProductType]
0x180027f3b  lea     rcx, aNetrenumeratec_4; "NetrEnumerateComputerNames: Not support"...
0x180027f42  call    cs:__imp_NetpLogPrintHelper
0x180027f48  mov     ebx, 32h ; '2'
0x180027f4d  mov     rcx, [rbp+Buffer]; Buffer
0x180027f51  test    rcx, rcx
0x180027f54  jz      short loc_180027F5C
0x180027f56  call    cs:__imp_NetApiBufferFree
0x180027f5c  call    IsNetpManageIPCConnectPresent
0x180027f61  test    al, al
0x180027f63  jz      short loc_180027F74
0x180027f65  mov     edx, ebx
0x180027f67  lea     rcx, aNetrenumeratec_0; "NetrEnumerateComputerNames: Failed 0x%l"...
0x180027f6e  call    cs:__imp_NetpLogPrintHelper
0x180027f74  mov     rcx, [rbp+Src]; Buffer
0x180027f78  test    rcx, rcx
0x180027f7b  jz      short loc_180027F83
0x180027f7d  call    cs:__imp_NetApiBufferFree
0x180027f83  call    IsNetpManageIPCConnectPresent
0x180027f88  test    al, al
0x180027f8a  jz      short loc_180027F92
0x180027f8c  call    cs:__imp_NetSetuppCloseLog
0x180027f92  mov     eax, ebx
0x180027f94  add     rsp, 68h
0x180027f98  pop     r15
0x180027f9a  pop     r14
0x180027f9c  pop     r13
0x180027f9e  pop     r12
0x180027fa0  pop     rdi
0x180027fa1  pop     rsi
0x180027fa2  pop     rbx
0x180027fa3  pop     rbp
0x180027fa4  retn
0x180027fa5  test    ebx, ebx
0x180027fa7  jz      short loc_180027FCB
0x180027fa9  test    sil, bl
0x180027fac  jnz     short loc_180027FCB
0x180027fae  call    IsNetpManageIPCConnectPresent
0x180027fb3  test    al, al
0x180027fb5  jz      short loc_180027FC4
0x180027fb7  lea     rcx, aNetrenumeratec_2; "NetrEnumerateComputerNames: Invalid Fla"...
0x180027fbe  call    cs:__imp_NetpLogPrintHelper
0x180027fc4  mov     ebx, 3ECh
0x180027fc9  jmp     short loc_180027F4D
0x180027fcb  cmp     edi, 3
0x180027fce  jl      short loc_180027FF2
0x180027fd0  call    IsNetpManageIPCConnectPresent
0x180027fd5  test    al, al
0x180027fd7  jz      short loc_180027FE8
0x180027fd9  mov     edx, edi
0x180027fdb  lea     rcx, aNetrenumeratec_3; "NetrEnumerateComputerNames: Invalid nam"...
0x180027fe2  call    cs:__imp_NetpLogPrintHelper
0x180027fe8  mov     ebx, 57h ; 'W'
0x180027fed  jmp     loc_180027F4D
0x180027ff2  xor     edx, edx
0x180027ff4  xor     ecx, ecx
0x180027ff6  call    WsImpersonateClient2
0x180027ffb  mov     ebx, eax
0x180027ffd  test    eax, eax
0x180027fff  jz      short loc_180028022
0x180028001  call    IsNetpManageIPCConnectPresent
0x180028006  test    al, al
0x180028008  jz      loc_180027F4D
0x18002800e  mov     edx, ebx
0x180028010  lea     rcx, aNetrenumeratec_6; "NetrEnumerateComputerNames: WsImpersona"...
0x180028017  call    cs:__imp_NetpLogPrintHelper
0x18002801d  jmp     loc_180027F4D
0x180028022  mov     r8, [rbp+Src]
0x180028026  lea     r9, [rbp+var_28]
0x18002802a  xor     edx, edx
0x18002802c  mov     ecx, edi
0x18002802e  call    cs:__imp_EnumerateLocalComputerNamesW
0x180028034  mov     ebx, eax
0x180028036  test    eax, eax
0x180028038  jz      short loc_18002805A
0x18002803a  cmp     eax, 0EAh
0x18002803f  jnz     short loc_180028088
0x180028041  mov     ecx, [rbp+var_28]
0x180028044  lea     rdx, [rbp+Src]; Buffer
0x180028048  add     ecx, ecx; ByteCount
0x18002804a  call    cs:__imp_NetApiBufferAllocate
0x180028050  mov     ebx, eax
0x180028052  test    eax, eax
0x180028054  jnz     loc_18002811F
0x18002805a  mov     r8, [rbp+Src]
0x18002805e  lea     r9, [rbp+var_28]
0x180028062  xor     edx, edx
0x180028064  mov     ecx, edi
0x180028066  call    cs:__imp_EnumerateLocalComputerNamesW
0x18002806c  mov     ebx, eax
0x18002806e  test    eax, eax
0x180028070  jz      short loc_1800280A6
0x180028072  call    IsNetpManageIPCConnectPresent
0x180028077  test    al, al
0x180028079  jz      loc_18002811F
0x18002807f  lea     rcx, aNetrenumeratec; "NetrEnumerateComputerNames: EnumerateLo"...
0x180028086  jmp     short loc_18002809C
0x180028088  call    IsNetpManageIPCConnectPresent
0x18002808d  test    al, al
0x18002808f  jz      loc_18002811F
0x180028095  lea     rcx, aNetrenumeratec_5; "NetrEnumerateComputerNames: EnumerateLo"...
0x18002809c  mov     edx, ebx
0x18002809e  call    cs:__imp_NetpLogPrintHelper
0x1800280a4  jmp     short loc_18002811F
0x1800280a6  mov     rdx, [rbp+Src]
0x1800280aa  mov     r8d, 10h
0x1800280b0  mov     [rbp+var_28], r8d
0x1800280b4  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800280b8  mov     edi, r13d
0x1800280bb  mov     ecx, r8d
0x1800280be  cmp     [rdx], r13w
0x1800280c2  jz      short loc_1800280F3
0x1800280c4  mov     rax, r9
0x1800280c7  inc     rax
0x1800280ca  cmp     [rdx+rax*2], r13w
0x1800280cf  jnz     short loc_1800280C7
0x1800280d1  lea     eax, [rax+9]
0x1800280d4  add     edi, esi
0x1800280d6  lea     r8d, [rcx+rax*2]
0x1800280da  mov     rax, r9
0x1800280dd  mov     [rbp+var_28], r8d
0x1800280e1  inc     rax
0x1800280e4  cmp     [rdx+rax*2], r13w
0x1800280e9  jnz     short loc_1800280E1
0x1800280eb  inc     eax
0x1800280ed  lea     rdx, [rdx+rax*2]
0x1800280f1  jmp     short loc_1800280BB
0x1800280f3  lea     rdx, [rbp+Buffer]; Buffer
0x1800280f7  mov     ecx, r8d; ByteCount
0x1800280fa  call    cs:__imp_NetApiBufferAllocate
0x180028100  mov     ebx, eax
0x180028102  test    eax, eax
0x180028104  jnz     short loc_18002811F
0x180028106  mov     rax, [rbp+Buffer]
0x18002810a  mov     [rax], edi
0x18002810c  mov     rax, [rbp+Buffer]
0x180028110  test    edi, edi
0x180028112  jnz     loc_1800281AA
0x180028118  mov     [rax+8], r13
0x18002811c  mov     ebx, r13d
0x18002811f  xor     edx, edx
0x180028121  xor     ecx, ecx
0x180028123  call    WsRevertToSelf2
0x180028128  test    ebx, ebx
0x18002812a  jnz     loc_180027F4D
0x180028130  mov     rax, [rbp+Buffer]
0x180028134  mov     [r12], rax
0x180028138  cmp     [rax], r13d
0x18002813b  jbe     loc_18002822B
0x180028141  call    IsNetpManageIPCConnectPresent
0x180028146  test    al, al
0x180028148  jz      short loc_180028157
0x18002814a  lea     rcx, aNetrenumeratec_1; "NetrEnumerateComputerNames: Returning n"...
0x180028151  call    cs:__imp_NetpLogPrintHelper
0x180028157  mov     rax, [rbp+Buffer]
0x18002815b  mov     edi, r13d
0x18002815e  cmp     [rax], r13d
0x180028161  jbe     short loc_180028191
0x180028163  call    IsNetpManageIPCConnectPresent
0x180028168  test    al, al
0x18002816a  jz      short loc_180028187
0x18002816c  mov     rax, [rbp+Buffer]
0x180028170  lea     rcx, aWz; " %wZ"
0x180028177  mov     edx, edi
0x180028179  shl     rdx, 4
0x18002817d  add     rdx, [rax+8]
0x180028181  call    cs:__imp_NetpLogPrintHelper
0x180028187  mov     rax, [rbp+Buffer]
0x18002818b  add     edi, esi
0x18002818d  cmp     edi, [rax]
0x18002818f  jb      short loc_180028163
0x180028191  call    IsNetpManageIPCConnectPresent
0x180028196  test    al, al
0x180028198  jz      loc_180027F74
0x18002819e  lea     rcx, asc_18004078C; "\n"
0x1800281a5  jmp     loc_18002823F
0x1800281aa  lea     r14, [rax+10h]
0x1800281ae  shl     rdi, 4
0x1800281b2  mov     [rax+8], r14
0x1800281b6  add     rdi, r14
0x1800281b9  mov     rbx, [rbp+Src]
0x1800281bd  mov     r15d, r13d
0x1800281c0  cmp     [rbx], r13w
0x1800281c4  jz      loc_18002811C
0x1800281ca  mov     esi, r15d
0x1800281cd  add     rsi, rsi
0x1800281d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800281d4  mov     [r14+rsi*8+8], rdi
0x1800281d9  inc     rax
0x1800281dc  cmp     [rbx+rax*2], r13w
0x1800281e1  jnz     short loc_1800281D9
0x1800281e3  add     ax, ax
0x1800281e6  mov     rdx, rbx; Src
0x1800281e9  mov     [r14+rsi*8], ax
0x1800281ee  mov     rcx, rdi; void *
0x1800281f1  add     ax, 2
0x1800281f5  movzx   r8d, ax; Size
0x1800281f9  mov     [r14+rsi*8+2], r8w
0x1800281ff  call    memcpy_0
0x180028204  movzx   eax, word ptr [r14+rsi*8+2]
0x18002820a  mov     esi, 1
0x18002820f  add     r15d, esi
0x180028212  add     rdi, rax
0x180028215  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028219  inc     rax
0x18002821c  cmp     [rbx+rax*2], r13w
0x180028221  jnz     short loc_180028219
0x180028223  inc     eax
0x180028225  lea     rbx, [rbx+rax*2]
0x180028229  jmp     short loc_1800281C0
0x18002822b  call    IsNetpManageIPCConnectPresent
0x180028230  test    al, al
0x180028232  jz      loc_180027F74
0x180028238  lea     rcx, aNetrenumeratec_7; "NetrEnumerateComputerNames: No names re"...
0x18002823f  call    cs:__imp_NetpLogPrintHelper
0x180028245  jmp     loc_180027F74
```

# IppInitializeIpsServiceChain

- ea: `0x1400437b4`
- end: `0x1400439fb`
- name: `IppInitializeIpsServiceChain`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004258c`

## callees

- `0x14003f5ac`
- `0x140040a3c`
- `0x1400424a4`
- `0x1400437b4`
- `0x140044ef4`
- `0x140053e98`
- `0x140152820`
- `0x14018daf0`
- `0x14018dd58`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401c345f`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401c345f`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140043859`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140043859`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400438db`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400438db`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140043887`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140043887`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400438cf`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400438cf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004389f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004389f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c3471`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c3471`
- `ntoskrnl!ExAllocatePool2` at `0x1400437fc`
- `ntoskrnl!ExAllocatePool2` at `0x1400437fc`

## string_xrefs

- `0x14004387b`: `IPS service chain rundown object (IPNG)`
- `0x140043997`: `IPS service chain (IPNG)`

## pseudocode

```c
__int64 __fastcall IppInitializeIpsServiceChain(__int64 a1, _OWORD *a2)
{
  __int64 v4; // rdi
  __int64 Pool2; // rax
  __int64 v6; // r8
  _QWORD *v7; // rbx
  unsigned int v8; // edi
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  const wchar_t *v10; // r9
  __int64 v11; // rbp
  __int64 v12; // rcx
  PDEVICE_OBJECT v13; // rcx
  unsigned int v14; // r8d
  _QWORD *v15; // r14
  _QWORD *i; // rdi
  __int64 v18; // rax
  int inserted; // eax
  __int64 v20; // r9
  unsigned int j; // edx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v22; // rcx
  __int64 v23; // rcx

  v4 = *(_QWORD *)(*(_QWORD *)a1 + 40LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_ac85ee5d021131934f4c5188022bc398_Traceguids,
      *(unsigned int *)(a1 + 8));
  }
  Pool2 = ExAllocatePool2(64, 48, 1884508233);
  v7 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741670;
    if ( SBYTE3(WPP_MAIN_CB.Reserved) >= 0 )
    {
LABEL_5:
      if ( *(_QWORD *)(a1 + 96) )
        IppCleanupIpsServiceChain(a1, *(_QWORD *)(*(_QWORD *)a1 + 40LL));
      if ( v7 )
      {
        v22 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)v7[2];
        if ( v22 )
          ExFreeCacheAwareRundownProtection(v22);
        ExFreePoolWithTag(v7, 0x70535049u);
      }
      return v8;
    }
    v10 = L"IPS service chain (IPNG)";
LABEL_29:
    McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCPIP_MEMORY_FAILURES, v6, v10);
    goto LABEL_5;
  }
  *(_OWORD *)(Pool2 + 24) = *a2;
  *(_QWORD *)(Pool2 + 8) = Pool2;
  *(_QWORD *)Pool2 = Pool2;
  CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x70535049u);
  v7[2] = CacheAwareRundownProtection;
  if ( !CacheAwareRundownProtection )
  {
    v8 = -1073741670;
    if ( SBYTE3(WPP_MAIN_CB.Reserved) >= 0 )
      goto LABEL_5;
    v10 = L"IPS service chain rundown object (IPNG)";
    goto LABEL_29;
  }
  KeEnterCriticalRegion();
  v11 = v4 + 19632;
  ExAcquirePushLockExclusiveEx(v4 + 19632, 0);
  IppDisableIpsServiceChain(v12, v7);
  v15 = (_QWORD *)(v4 + 19640);
  for ( i = *(_QWORD **)(v4 + 19640); i != v15; i = (_QWORD *)*i )
  {
    v18 = i[16];
    if ( v18 )
    {
      v14 = *(_DWORD *)(v18 + 4);
      v20 = v18 + 8;
      for ( j = 0; j < v14; ++j )
      {
        v23 = v7[3] - *(_QWORD *)v20;
        if ( !v23 )
          v23 = v7[4] - *(_QWORD *)(v20 + 8);
        if ( !v23 )
        {
          inserted = IppInsertIpsClientToServiceChain(a1, (_DWORD)v7, (_DWORD)i, *(_DWORD *)(v20 + 16), 0);
          if ( inserted >= 0 )
            goto LABEL_20;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
          {
            WPP_SF_SDd(WPP_GLOBAL_Control->AttachedDevice, 23, v14, (_DWORD)i + 28, *(_DWORD *)(a1 + 8), inserted);
          }
          goto LABEL_12;
        }
        v20 += 20;
      }
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800000) != 0 )
    {
      WPP_SF_DS(WPP_GLOBAL_Control->AttachedDevice, 24, v14, *(_DWORD *)(a1 + 8), (__int64)i + 28);
    }
LABEL_20:
    ;
  }
LABEL_12:
  IppEnableIpsServiceChain(v13, v7);
  ExReleasePushLockExclusiveEx(v11, 0);
  KeLeaveCriticalRegion();
  v8 = 0;
  *(_QWORD *)(a1 + 96) = v7;
  return v8;
}

```

## disassembly

```asm
0x1400437b4  push    rbx
0x1400437b6  push    rbp
0x1400437b7  push    rsi
0x1400437b8  push    rdi
0x1400437b9  push    r13
0x1400437bb  push    r14
0x1400437bd  sub     rsp, 38h
0x1400437c1  mov     rax, [rcx]
0x1400437c4  mov     rbp, rdx
0x1400437c7  mov     rsi, rcx
0x1400437ca  mov     rdi, [rax+28h]
0x1400437ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400437d5  lea     r13, WPP_GLOBAL_Control
0x1400437dc  cmp     rcx, r13
0x1400437df  jz      short loc_1400437EB
0x1400437e1  cmp     byte ptr [rcx+29h], 4
0x1400437e5  jnb     loc_14004396C
0x1400437eb  mov     edx, 30h ; '0'
0x1400437f0  mov     r14d, 70535049h
0x1400437f6  mov     r8d, r14d
0x1400437f9  lea     ecx, [rdx+10h]
0x1400437fc  call    cs:__imp_ExAllocatePool2
0x140043803  nop     dword ptr [rax+rax+00h]
0x140043808  mov     rbx, rax
0x14004380b  test    rax, rax
0x14004380e  jnz     short loc_140043841
0x140043810  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x140043816  mov     edi, 0C000009Ah
0x14004381b  jl      loc_140043997
0x140043821  cmp     qword ptr [rsi+60h], 0
0x140043826  jz      loc_1401C344D
0x14004382c  mov     rdx, [rsi]
0x14004382f  mov     rcx, rsi
0x140043832  mov     rdx, [rdx+28h]
0x140043836  call    IppCleanupIpsServiceChain
0x14004383b  nop
0x14004383c  jmp     loc_1401C344D
0x140043841  movups  xmm0, xmmword ptr [rbp+0]
0x140043845  mov     edx, r14d; PoolTag
0x140043848  mov     ecx, 200h; PoolType
0x14004384d  movdqu  xmmword ptr [rax+18h], xmm0
0x140043852  mov     [rax+8], rbx
0x140043856  mov     [rax], rbx
0x140043859  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140043860  nop     dword ptr [rax+rax+00h]
0x140043865  mov     [rbx+10h], rax
0x140043869  test    rax, rax
0x14004386c  jnz     short loc_140043887
0x14004386e  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x140043874  mov     edi, 0C000009Ah
0x140043879  jge     short loc_140043821
0x14004387b  lea     r9, aIpsServiceChai_0; "IPS service chain rundown object (IPNG)"
0x140043882  jmp     loc_1401C3434
0x140043887  call    cs:__imp_KeEnterCriticalRegion
0x14004388e  nop     dword ptr [rax+rax+00h]
0x140043893  lea     rbp, [rdi+4CB0h]
0x14004389a  xor     edx, edx
0x14004389c  mov     rcx, rbp
0x14004389f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400438a6  nop     dword ptr [rax+rax+00h]
0x1400438ab  mov     rdx, rbx
0x1400438ae  call    IppDisableIpsServiceChain
0x1400438b3  lea     r14, [rdi+4CB8h]
0x1400438ba  mov     rdi, [r14]
0x1400438bd  cmp     rdi, r14
0x1400438c0  jnz     short loc_1400438FD
0x1400438c2  mov     rdx, rbx
0x1400438c5  call    IppEnableIpsServiceChain
0x1400438ca  xor     edx, edx
0x1400438cc  mov     rcx, rbp
0x1400438cf  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400438d6  nop     dword ptr [rax+rax+00h]
0x1400438db  call    cs:__imp_KeLeaveCriticalRegion
0x1400438e2  nop     dword ptr [rax+rax+00h]
0x1400438e7  xor     edi, edi
0x1400438e9  mov     [rsi+60h], rbx
0x1400438ed  mov     eax, edi
0x1400438ef  add     rsp, 38h
0x1400438f3  pop     r14
0x1400438f5  pop     r13
0x1400438f7  pop     rdi
0x1400438f8  pop     rsi
0x1400438f9  pop     rbp
0x1400438fa  pop     rbx
0x1400438fb  retn
0x1400438fd  mov     rax, [rdi+80h]
0x140043904  test    rax, rax
0x140043907  jnz     loc_1400439A3
0x14004390d  mov     rcx, cs:WPP_GLOBAL_Control
0x140043914  cmp     rcx, r13
0x140043917  jz      short loc_140043964
0x140043919  cmp     byte ptr [rcx+29h], 4
0x14004391d  jb      short loc_140043964
0x14004391f  test    dword ptr [rcx+2Ch], 800000h
0x140043926  jz      short loc_140043964
0x140043928  mov     r9d, [rsi+8]
0x14004392c  lea     rax, [rdi+1Ch]
0x140043930  mov     rcx, [rcx+18h]
0x140043934  mov     edx, 18h
0x140043939  mov     [rsp+68h+var_48], rax
0x14004393e  call    WPP_SF_DS
0x140043943  jmp     short loc_140043964
0x140043945  mov     r9d, [r9+10h]
0x140043949  mov     r8, rdi
0x14004394c  mov     rdx, rbx
0x14004394f  mov     [rsp+68h+var_48], 0
0x140043958  mov     rcx, rsi
0x14004395b  call    IppInsertIpsClientToServiceChain
0x140043960  test    eax, eax
0x140043962  js      short loc_1400439B2
0x140043964  mov     rdi, [rdi]
0x140043967  jmp     loc_1400438BD
0x14004396c  test    dword ptr [rcx+2Ch], 800000h
0x140043973  jz      loc_1400437EB
0x140043979  mov     r9d, [rsi+8]
0x14004397d  lea     r8, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids
0x140043984  mov     rcx, [rcx+18h]
0x140043988  mov     edx, 16h
0x14004398d  call    WPP_SF_d
0x140043992  jmp     loc_1400437EB
0x140043997  lea     r9, aIpsServiceChai_1; "IPS service chain (IPNG)"
0x14004399e  jmp     loc_1401C3434
0x1400439a3  mov     r8d, [rax+4]
0x1400439a7  lea     r9, [rax+8]
0x1400439ab  xor     edx, edx
0x1400439ad  jmp     loc_1401C3483
0x1400439b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400439b9  cmp     rcx, r13
0x1400439bc  jz      loc_1400438C2
0x1400439c2  cmp     byte ptr [rcx+29h], 2
0x1400439c6  jb      loc_1400438C2
0x1400439cc  test    dword ptr [rcx+2Ch], 800000h
0x1400439d3  jz      loc_1400438C2
0x1400439d9  mov     rcx, [rcx+18h]
0x1400439dd  lea     r9, [rdi+1Ch]
0x1400439e1  mov     [rsp+68h+var_40], eax
0x1400439e5  mov     edx, 17h
0x1400439ea  mov     eax, [rsi+8]
0x1400439ed  mov     dword ptr [rsp+68h+var_48], eax
0x1400439f1  call    WPP_SF_SDd
0x1400439f6  jmp     loc_1400438C2
0x1401c3434  lea     rdx, TCPIP_MEMORY_FAILURES
0x1401c343b  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401c3442  call    McTemplateK0z_EtwWriteTransfer
0x1401c3447  nop
0x1401c3448  jmp     loc_140043821
0x1401c344d  test    rbx, rbx
0x1401c3450  jz      loc_1400438ED
0x1401c3456  mov     rcx, [rbx+10h]; RunRefCacheAware
0x1401c345a  test    rcx, rcx
0x1401c345d  jz      short loc_1401C346B
0x1401c345f  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1401c3466  nop     dword ptr [rax+rax+00h]
0x1401c346b  mov     edx, r14d; Tag
0x1401c346e  mov     rcx, rbx; P
0x1401c3471  call    cs:__imp_ExFreePoolWithTag
0x1401c3478  nop     dword ptr [rax+rax+00h]
0x1401c347d  nop
0x1401c347e  jmp     loc_1400438ED
0x1401c3483  cmp     edx, r8d
0x1401c3486  jnb     loc_14004390D
0x1401c348c  mov     rcx, [rbx+18h]
0x1401c3490  sub     rcx, [r9]
0x1401c3493  jnz     short loc_1401C349D
0x1401c3495  mov     rcx, [rbx+20h]
0x1401c3499  sub     rcx, [r9+8]
0x1401c349d  test    rcx, rcx
0x1401c34a0  jz      loc_140043945
0x1401c34a6  add     r9, 14h
0x1401c34aa  inc     edx
0x1401c34ac  jmp     short loc_1401C3483
```

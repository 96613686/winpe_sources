# IppInitializeIpsServiceChain

- ea: `0x140043a54`
- end: `0x140043c9b`
- name: `IppInitializeIpsServiceChain`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004282c`

## callees

- `0x14003f84c`
- `0x140040cdc`
- `0x140042744`
- `0x140043a54`
- `0x140045194`
- `0x140054138`
- `0x140152960`
- `0x14018dc30`
- `0x14018de98`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401c359f`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1401c359f`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140043af9`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x140043af9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140043b7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140043b7b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140043b27`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140043b27`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140043b6f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140043b6f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140043b3f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140043b3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c35b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c35b1`
- `ntoskrnl!ExAllocatePool2` at `0x140043a9c`
- `ntoskrnl!ExAllocatePool2` at `0x140043a9c`

## string_xrefs

- `0x140043c37`: `IPS service chain (IPNG)`
- `0x140043b1b`: `IPS service chain rundown object (IPNG)`

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
      &WPP_ac85ee5d021131934f4c5188022bc398_Traceguids,
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
    McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, &TCPIP_MEMORY_FAILURES, v6, v10);
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
0x140043a54  push    rbx
0x140043a56  push    rbp
0x140043a57  push    rsi
0x140043a58  push    rdi
0x140043a59  push    r13
0x140043a5b  push    r14
0x140043a5d  sub     rsp, 38h
0x140043a61  mov     rax, [rcx]
0x140043a64  mov     rbp, rdx
0x140043a67  mov     rsi, rcx
0x140043a6a  mov     rdi, [rax+28h]
0x140043a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x140043a75  lea     r13, WPP_GLOBAL_Control
0x140043a7c  cmp     rcx, r13
0x140043a7f  jz      short loc_140043A8B
0x140043a81  cmp     byte ptr [rcx+29h], 4
0x140043a85  jnb     loc_140043C0C
0x140043a8b  mov     edx, 30h ; '0'
0x140043a90  mov     r14d, 70535049h
0x140043a96  mov     r8d, r14d
0x140043a99  lea     ecx, [rdx+10h]
0x140043a9c  call    cs:__imp_ExAllocatePool2
0x140043aa3  nop     dword ptr [rax+rax+00h]
0x140043aa8  mov     rbx, rax
0x140043aab  test    rax, rax
0x140043aae  jnz     short loc_140043AE1
0x140043ab0  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x140043ab6  mov     edi, 0C000009Ah
0x140043abb  jl      loc_140043C37
0x140043ac1  cmp     qword ptr [rsi+60h], 0
0x140043ac6  jz      loc_1401C358D
0x140043acc  mov     rdx, [rsi]
0x140043acf  mov     rcx, rsi
0x140043ad2  mov     rdx, [rdx+28h]
0x140043ad6  call    IppCleanupIpsServiceChain
0x140043adb  nop
0x140043adc  jmp     loc_1401C358D
0x140043ae1  movups  xmm0, xmmword ptr [rbp+0]
0x140043ae5  mov     edx, r14d; PoolTag
0x140043ae8  mov     ecx, 200h; PoolType
0x140043aed  movdqu  xmmword ptr [rax+18h], xmm0
0x140043af2  mov     [rax+8], rbx
0x140043af6  mov     [rax], rbx
0x140043af9  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x140043b00  nop     dword ptr [rax+rax+00h]
0x140043b05  mov     [rbx+10h], rax
0x140043b09  test    rax, rax
0x140043b0c  jnz     short loc_140043B27
0x140043b0e  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x140043b14  mov     edi, 0C000009Ah
0x140043b19  jge     short loc_140043AC1
0x140043b1b  lea     r9, aIpsServiceChai_0; "IPS service chain rundown object (IPNG)"
0x140043b22  jmp     loc_1401C3574
0x140043b27  call    cs:__imp_KeEnterCriticalRegion
0x140043b2e  nop     dword ptr [rax+rax+00h]
0x140043b33  lea     rbp, [rdi+4CB0h]
0x140043b3a  xor     edx, edx
0x140043b3c  mov     rcx, rbp
0x140043b3f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140043b46  nop     dword ptr [rax+rax+00h]
0x140043b4b  mov     rdx, rbx
0x140043b4e  call    IppDisableIpsServiceChain
0x140043b53  lea     r14, [rdi+4CB8h]
0x140043b5a  mov     rdi, [r14]
0x140043b5d  cmp     rdi, r14
0x140043b60  jnz     short loc_140043B9D
0x140043b62  mov     rdx, rbx
0x140043b65  call    IppEnableIpsServiceChain
0x140043b6a  xor     edx, edx
0x140043b6c  mov     rcx, rbp
0x140043b6f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140043b76  nop     dword ptr [rax+rax+00h]
0x140043b7b  call    cs:__imp_KeLeaveCriticalRegion
0x140043b82  nop     dword ptr [rax+rax+00h]
0x140043b87  xor     edi, edi
0x140043b89  mov     [rsi+60h], rbx
0x140043b8d  mov     eax, edi
0x140043b8f  add     rsp, 38h
0x140043b93  pop     r14
0x140043b95  pop     r13
0x140043b97  pop     rdi
0x140043b98  pop     rsi
0x140043b99  pop     rbp
0x140043b9a  pop     rbx
0x140043b9b  retn
0x140043b9d  mov     rax, [rdi+80h]
0x140043ba4  test    rax, rax
0x140043ba7  jnz     loc_140043C43
0x140043bad  mov     rcx, cs:WPP_GLOBAL_Control
0x140043bb4  cmp     rcx, r13
0x140043bb7  jz      short loc_140043C04
0x140043bb9  cmp     byte ptr [rcx+29h], 4
0x140043bbd  jb      short loc_140043C04
0x140043bbf  test    dword ptr [rcx+2Ch], 800000h
0x140043bc6  jz      short loc_140043C04
0x140043bc8  mov     r9d, [rsi+8]
0x140043bcc  lea     rax, [rdi+1Ch]
0x140043bd0  mov     rcx, [rcx+18h]
0x140043bd4  mov     edx, 18h
0x140043bd9  mov     [rsp+68h+var_48], rax
0x140043bde  call    WPP_SF_DS
0x140043be3  jmp     short loc_140043C04
0x140043be5  mov     r9d, [r9+10h]
0x140043be9  mov     r8, rdi
0x140043bec  mov     rdx, rbx
0x140043bef  mov     [rsp+68h+var_48], 0
0x140043bf8  mov     rcx, rsi
0x140043bfb  call    IppInsertIpsClientToServiceChain
0x140043c00  test    eax, eax
0x140043c02  js      short loc_140043C52
0x140043c04  mov     rdi, [rdi]
0x140043c07  jmp     loc_140043B5D
0x140043c0c  test    dword ptr [rcx+2Ch], 800000h
0x140043c13  jz      loc_140043A8B
0x140043c19  mov     r9d, [rsi+8]
0x140043c1d  lea     r8, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids
0x140043c24  mov     rcx, [rcx+18h]
0x140043c28  mov     edx, 16h
0x140043c2d  call    WPP_SF_d
0x140043c32  jmp     loc_140043A8B
0x140043c37  lea     r9, aIpsServiceChai_1; "IPS service chain (IPNG)"
0x140043c3e  jmp     loc_1401C3574
0x140043c43  mov     r8d, [rax+4]
0x140043c47  lea     r9, [rax+8]
0x140043c4b  xor     edx, edx
0x140043c4d  jmp     loc_1401C35C3
0x140043c52  mov     rcx, cs:WPP_GLOBAL_Control
0x140043c59  cmp     rcx, r13
0x140043c5c  jz      loc_140043B62
0x140043c62  cmp     byte ptr [rcx+29h], 2
0x140043c66  jb      loc_140043B62
0x140043c6c  test    dword ptr [rcx+2Ch], 800000h
0x140043c73  jz      loc_140043B62
0x140043c79  mov     rcx, [rcx+18h]
0x140043c7d  lea     r9, [rdi+1Ch]
0x140043c81  mov     [rsp+68h+var_40], eax
0x140043c85  mov     edx, 17h
0x140043c8a  mov     eax, [rsi+8]
0x140043c8d  mov     dword ptr [rsp+68h+var_48], eax
0x140043c91  call    WPP_SF_SDd
0x140043c96  jmp     loc_140043B62
0x1401c3574  lea     rdx, TCPIP_MEMORY_FAILURES
0x1401c357b  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1401c3582  call    McTemplateK0z_EtwWriteTransfer
0x1401c3587  nop
0x1401c3588  jmp     loc_140043AC1
0x1401c358d  test    rbx, rbx
0x1401c3590  jz      loc_140043B8D
0x1401c3596  mov     rcx, [rbx+10h]; RunRefCacheAware
0x1401c359a  test    rcx, rcx
0x1401c359d  jz      short loc_1401C35AB
0x1401c359f  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1401c35a6  nop     dword ptr [rax+rax+00h]
0x1401c35ab  mov     edx, r14d; Tag
0x1401c35ae  mov     rcx, rbx; P
0x1401c35b1  call    cs:__imp_ExFreePoolWithTag
0x1401c35b8  nop     dword ptr [rax+rax+00h]
0x1401c35bd  nop
0x1401c35be  jmp     loc_140043B8D
0x1401c35c3  cmp     edx, r8d
0x1401c35c6  jnb     loc_140043BAD
0x1401c35cc  mov     rcx, [rbx+18h]
0x1401c35d0  sub     rcx, [r9]
0x1401c35d3  jnz     short loc_1401C35DD
0x1401c35d5  mov     rcx, [rbx+20h]
0x1401c35d9  sub     rcx, [r9+8]
0x1401c35dd  test    rcx, rcx
0x1401c35e0  jz      loc_140043BE5
0x1401c35e6  add     r9, 14h
0x1401c35ea  inc     edx
0x1401c35ec  jmp     short loc_1401C35C3
```

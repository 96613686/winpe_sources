# NvmeAdapterRemoveSubsystemPortMiniport

- ea: `0x1400fca64`
- end: `0x1400fcbfc`
- name: `NvmeAdapterRemoveSubsystemPortMiniport`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400a0970`

## callees

- `0x140078b48`
- `0x1400f3fa0`
- `0x1400fa1d0`
- `0x1400fca64`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fcaf7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fcaf7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fcb0f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fcb0f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fcb49`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fcb49`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400fcb65`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400fcb65`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fcb55`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fcb55`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400fca81`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400fca81`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400fcbd2`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x1400fcbd2`

## pseudocode

```c
__int64 __fastcall NvmeAdapterRemoveSubsystemPortMiniport(__int64 a1, PEX_RUNDOWN_REF_CACHE_AWARE *a2)
{
  int v4; // ebx
  PEX_RUNDOWN_REF_CACHE_AWARE v6; // rax
  PEX_RUNDOWN_REF_CACHE_AWARE v7; // rbp
  PEX_RUNDOWN_REF_CACHE_AWARE v8; // r8
  PEX_RUNDOWN_REF_CACHE_AWARE **v9; // rdx
  PEX_RUNDOWN_REF_CACHE_AWARE *v10; // [rsp+88h] [rbp+10h] BYREF

  v10 = a2;
  if ( KeGetCurrentIrql() )
  {
    return (unsigned int)-1056964600;
  }
  else
  {
    if ( (*(_BYTE *)(a1 + 152) & 1) == 0 )
      return (unsigned int)-1073741637;
    if ( *(_DWORD *)a2 != 1314280272 )
      return (unsigned int)-1073741811;
    v6 = a2[4];
    if ( ((unsigned __int8)v6 & 1) != 0 )
    {
      return (unsigned int)-1073741637;
    }
    else if ( ((unsigned __int8)v6 & 0x10) != 0 )
    {
      return (unsigned int)-2147483631;
    }
    else
    {
      v7 = a2[3];
      v4 = NvmeAdapterHostGatewayAcquireRundown(v7);
      if ( v4 >= 0 )
      {
        a2[4] = (PEX_RUNDOWN_REF_CACHE_AWARE)((unsigned __int64)a2[4] | 0x10);
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite((PERESOURCE)((char *)v7 + 384), 1u);
        v8 = a2[1];
        if ( *((PEX_RUNDOWN_REF_CACHE_AWARE **)v8 + 1) != a2 + 1
          || (v9 = (PEX_RUNDOWN_REF_CACHE_AWARE **)a2[2], *v9 != a2 + 1) )
        {
          __fastfail(3u);
        }
        *v9 = (PEX_RUNDOWN_REF_CACHE_AWARE *)v8;
        *((_QWORD *)v8 + 1) = v9;
        --*((_DWORD *)v7 + 94);
        ExReleaseResourceLite((PERESOURCE)((char *)v7 + 384));
        KeLeaveCriticalRegion();
        ExReleaseRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)v7 + 7));
        if ( (byte_14017743A & 4) != 0 )
          McTemplateK0qjzshsss_EtwWriteTransfer(
            (_DWORD)a2 + 316,
            (_DWORD)a2 + 60,
            (_DWORD)v7 + 72,
            *(_DWORD *)(a1 + 56),
            a1 + 1048,
            *(_QWORD *)(a1 + 1032),
            (__int64)v7 + 72,
            *((_WORD *)a2 + 2),
            (__int64)a2 + 60,
            (__int64)a2 + 316,
            (__int64)a2 + 572);
        ExWaitForRundownProtectionReleaseCacheAware(a2[5]);
        NvmeAdapterCleanupSubsystemPort(a1, 0, (PVOID *)&v10);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400fca64  mov     rax, rsp
0x1400fca67  mov     [rax+8], rbx
0x1400fca6b  mov     [rax+18h], rbp
0x1400fca6f  push    rsi
0x1400fca70  push    rdi
0x1400fca71  push    r14
0x1400fca73  sub     rsp, 60h
0x1400fca77  mov     rdi, rdx
0x1400fca7a  mov     [rax+10h], rdx
0x1400fca7e  mov     rsi, rcx
0x1400fca81  call    cs:__imp_KeGetCurrentIrql
0x1400fca88  nop     dword ptr [rax+rax+00h]
0x1400fca8d  test    al, al
0x1400fca8f  jz      short loc_1400FCAAE
0x1400fca91  mov     ebx, 0C1000008h
0x1400fca96  lea     r11, [rsp+78h+var_18]
0x1400fca9b  mov     eax, ebx
0x1400fca9d  mov     rbx, [r11+20h]
0x1400fcaa1  mov     rbp, [r11+30h]
0x1400fcaa5  mov     rsp, r11
0x1400fcaa8  pop     r14
0x1400fcaaa  pop     rdi
0x1400fcaab  pop     rsi
0x1400fcaac  retn
0x1400fcaae  test    byte ptr [rsi+98h], 1
0x1400fcab5  jnz     short loc_1400FCABE
0x1400fcab7  mov     ebx, 0C00000BBh
0x1400fcabc  jmp     short loc_1400FCA96
0x1400fcabe  cmp     dword ptr [rdi], 4E565350h
0x1400fcac4  jz      short loc_1400FCACD
0x1400fcac6  mov     ebx, 0C000000Dh
0x1400fcacb  jmp     short loc_1400FCA96
0x1400fcacd  mov     rax, [rdi+20h]
0x1400fcad1  test    al, 1
0x1400fcad3  jnz     short loc_1400FCAB7
0x1400fcad5  test    al, 10h
0x1400fcad7  jz      short loc_1400FCAE0
0x1400fcad9  mov     ebx, 80000011h
0x1400fcade  jmp     short loc_1400FCA96
0x1400fcae0  mov     rbp, [rdi+18h]
0x1400fcae4  mov     rcx, rbp
0x1400fcae7  call    NvmeAdapterHostGatewayAcquireRundown
0x1400fcaec  mov     ebx, eax
0x1400fcaee  test    eax, eax
0x1400fcaf0  js      short loc_1400FCA96
0x1400fcaf2  or      qword ptr [rdi+20h], 10h
0x1400fcaf7  call    cs:__imp_KeEnterCriticalRegion
0x1400fcafe  nop     dword ptr [rax+rax+00h]
0x1400fcb03  lea     r14, [rbp+180h]
0x1400fcb0a  mov     dl, 1; Wait
0x1400fcb0c  mov     rcx, r14; Resource
0x1400fcb0f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400fcb16  nop     dword ptr [rax+rax+00h]
0x1400fcb1b  lea     rax, [rdi+8]
0x1400fcb1f  mov     r8, [rax]
0x1400fcb22  cmp     [r8+8], rax
0x1400fcb26  jnz     loc_1400FCBF5
0x1400fcb2c  mov     rdx, [rax+8]
0x1400fcb30  cmp     [rdx], rax
0x1400fcb33  jnz     loc_1400FCBF5
0x1400fcb39  mov     [rdx], r8
0x1400fcb3c  mov     rcx, r14; Resource
0x1400fcb3f  mov     [r8+8], rdx
0x1400fcb43  dec     dword ptr [rbp+178h]
0x1400fcb49  call    cs:__imp_ExReleaseResourceLite
0x1400fcb50  nop     dword ptr [rax+rax+00h]
0x1400fcb55  call    cs:__imp_KeLeaveCriticalRegion
0x1400fcb5c  nop     dword ptr [rax+rax+00h]
0x1400fcb61  mov     rcx, [rbp+38h]; RunRefCacheAware
0x1400fcb65  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400fcb6c  nop     dword ptr [rax+rax+00h]
0x1400fcb71  test    cs:byte_14017743A, 4
0x1400fcb78  jz      short loc_1400FCBCE
0x1400fcb7a  lea     rax, [rdi+23Ch]
0x1400fcb81  mov     [rsp+78h+var_28], rax
0x1400fcb86  lea     r9, [rsi+418h]
0x1400fcb8d  movzx   eax, word ptr [rdi+4]
0x1400fcb91  lea     rcx, [rdi+13Ch]
0x1400fcb98  mov     [rsp+78h+var_30], rcx
0x1400fcb9d  lea     rdx, [rdi+3Ch]
0x1400fcba1  mov     [rsp+78h+var_38], rdx
0x1400fcba6  lea     r8, [rbp+48h]
0x1400fcbaa  mov     [rsp+78h+var_40], ax
0x1400fcbaf  mov     rax, [rsi+408h]
0x1400fcbb6  mov     [rsp+78h+var_48], r8
0x1400fcbbb  mov     [rsp+78h+var_50], rax
0x1400fcbc0  mov     [rsp+78h+var_58], r9
0x1400fcbc5  mov     r9d, [rsi+38h]
0x1400fcbc9  call    McTemplateK0qjzshsss_EtwWriteTransfer
0x1400fcbce  mov     rcx, [rdi+28h]; RunRef
0x1400fcbd2  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x1400fcbd9  nop     dword ptr [rax+rax+00h]
0x1400fcbde  lea     r8, [rsp+78h+arg_8]
0x1400fcbe6  xor     edx, edx
0x1400fcbe8  mov     rcx, rsi
0x1400fcbeb  call    NvmeAdapterCleanupSubsystemPort
0x1400fcbf0  jmp     loc_1400FCA96
0x1400fcbf5  mov     ecx, 3
0x1400fcbfa  int     29h; Win8: RtlFailFast(ecx)
```

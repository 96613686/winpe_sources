# NvmeAdapterRemoveHostGateway

- ea: `0x140078868`
- end: `0x140078b41`
- name: `NvmeAdapterRemoveHostGateway`
- size: `729`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400a0970`
- `0x1400fa09c`

## callees

- `0x140078868`
- `0x140078b48`
- `0x1400f3fa0`
- `0x1400f4304`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140078a9e`
- `ntoskrnl!ExDeleteResourceLite` at `0x140078a9e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400788ef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007896f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400788ef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007896f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140078901`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140078987`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140078901`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140078987`
- `ntoskrnl!ExReleaseResourceLite` at `0x140078947`
- `ntoskrnl!ExReleaseResourceLite` at `0x140078a83`
- `ntoskrnl!ExReleaseResourceLite` at `0x140078947`
- `ntoskrnl!ExReleaseResourceLite` at `0x140078a83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078b16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078b16`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140078953`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140078a8f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140078953`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140078a8f`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140078aae`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140078aae`
- `ntoskrnl!KeGetCurrentIrql` at `0x140078883`
- `ntoskrnl!KeGetCurrentIrql` at `0x140078883`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140078963`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140078a54`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140078963`
- `ntoskrnl!ExWaitForRundownProtectionReleaseCacheAware` at `0x140078a54`

## pseudocode

```c
__int64 __fastcall NvmeAdapterRemoveHostGateway(__int64 a1, _DWORD *a2, char a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  int v11; // ecx
  _QWORD **v12; // rbx
  _QWORD *v13; // r8
  _QWORD *v14; // rax
  _QWORD *v15; // rbp
  __int64 v16; // rax
  __int64 v17; // rdx
  int v18; // r8d
  _QWORD *v20; // [rsp+88h] [rbp+10h] BYREF

  if ( KeGetCurrentIrql() )
  {
    return (unsigned int)-1056964600;
  }
  else if ( (*(_BYTE *)(a1 + 152) & 1) != 0 && *(_QWORD *)(a1 + 616) )
  {
    if ( *a2 == 1314277447 )
    {
      v7 = *((_QWORD *)a2 + 6);
      if ( (v7 & 4) != 0 )
      {
        return (unsigned int)-2147483631;
      }
      else
      {
        *((_QWORD *)a2 + 6) = v7 | 4;
        if ( a3 )
        {
          v8 = *(_QWORD *)(a1 + 616);
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite((PERESOURCE)(v8 + 24), 1u);
          v9 = *((_QWORD *)a2 + 3);
          if ( *(_DWORD **)(v9 + 8) != a2 + 6 || (v10 = (_QWORD *)*((_QWORD *)a2 + 4), (_DWORD *)*v10 != a2 + 6) )
LABEL_22:
            __fastfail(3u);
          *v10 = v9;
          *(_QWORD *)(v9 + 8) = v10;
          --*(_DWORD *)(*(_QWORD *)(a1 + 616) + 16LL);
          ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 616) + 24LL));
          KeLeaveCriticalRegion();
        }
        ExWaitForRundownProtectionReleaseCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)a2 + 7));
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite((PERESOURCE)(a2 + 96), 1u);
        if ( a2[94] )
        {
          v12 = (_QWORD **)(a2 + 90);
          while ( 1 )
          {
            v13 = *v12;
            if ( *v12 == v12 )
              break;
            if ( (_QWORD **)v13[1] != v12 )
              goto LABEL_22;
            v14 = (_QWORD *)*v13;
            if ( *(_QWORD **)(*v13 + 8LL) != v13 )
              goto LABEL_22;
            *v12 = v14;
            v15 = v13 - 1;
            v14[1] = v12;
            --a2[94];
            v16 = v13[3];
            v20 = v13 - 1;
            if ( (v16 & 0x10) == 0 )
            {
              v15[4] = v16 | 0x10;
              if ( (byte_14017743A & 4) != 0 )
                McTemplateK0qjzshsss_EtwWriteTransfer(
                  v11,
                  (_DWORD)v13 + 308,
                  (_DWORD)v13 + 52,
                  *(_DWORD *)(a1 + 56),
                  a1 + 1048,
                  *(_QWORD *)(a1 + 1032),
                  (__int64)(a2 + 18),
                  *((_WORD *)v15 + 2),
                  (__int64)v13 + 52,
                  (__int64)v13 + 308,
                  (__int64)v15 + 572);
              ExWaitForRundownProtectionReleaseCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v15[5]);
              LOBYTE(v17) = 1;
              NvmeAdapterCleanupSubsystemPort(a1, v17, &v20);
            }
          }
        }
        v6 = 0;
        ExReleaseResourceLite((PERESOURCE)(a2 + 96));
        KeLeaveCriticalRegion();
        ExDeleteResourceLite((PERESOURCE)(a2 + 96));
        ExFreeCacheAwareRundownProtection(*((PEX_RUNDOWN_REF_CACHE_AWARE *)a2 + 7));
        if ( (byte_14017743A & 4) != 0 )
          McTemplateK0qjzuuss_EtwWriteTransfer(
            (_DWORD)a2 + 72,
            (unsigned int)EventNVMeoFHostGatewayRemoved,
            v18,
            *(_DWORD *)(a1 + 56),
            a1 + 1048,
            *(_QWORD *)(a1 + 1032),
            *((_BYTE *)a2 + 4),
            *((_BYTE *)a2 + 8),
            (__int64)(a2 + 18),
            (__int64)(a2 + 82));
        ExFreePoolWithTag(a2, 0x464E6152u);
      }
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    return (unsigned int)-1073741637;
  }
  return v6;
}

```

## disassembly

```asm
0x140078868  mov     [rsp+arg_0], rbx
0x14007886d  mov     [rsp+arg_10], rbp
0x140078872  push    rsi
0x140078873  push    rdi
0x140078874  push    r14
0x140078876  sub     rsp, 60h
0x14007887a  mov     bl, r8b
0x14007887d  mov     rdi, rdx
0x140078880  mov     rsi, rcx
0x140078883  call    cs:__imp_KeGetCurrentIrql
0x14007888a  nop     dword ptr [rax+rax+00h]
0x14007888f  test    al, al
0x140078891  jz      short loc_14007889D
0x140078893  mov     ebx, 0C1000008h
0x140078898  jmp     loc_140078B29
0x14007889d  test    byte ptr [rsi+98h], 1
0x1400788a4  jz      loc_140078B24
0x1400788aa  cmp     qword ptr [rsi+268h], 0
0x1400788b2  jz      loc_140078B24
0x1400788b8  cmp     dword ptr [rdi], 4E564847h
0x1400788be  jz      short loc_1400788CA
0x1400788c0  mov     ebx, 0C000000Dh
0x1400788c5  jmp     loc_140078B29
0x1400788ca  mov     rax, [rdi+30h]
0x1400788ce  test    al, 4
0x1400788d0  jz      short loc_1400788DC
0x1400788d2  mov     ebx, 80000011h
0x1400788d7  jmp     loc_140078B29
0x1400788dc  or      rax, 4
0x1400788e0  mov     [rdi+30h], rax
0x1400788e4  test    bl, bl
0x1400788e6  jz      short loc_14007895F
0x1400788e8  mov     rbx, [rsi+268h]
0x1400788ef  call    cs:__imp_KeEnterCriticalRegion
0x1400788f6  nop     dword ptr [rax+rax+00h]
0x1400788fb  mov     dl, 1; Wait
0x1400788fd  lea     rcx, [rbx+18h]; Resource
0x140078901  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140078908  nop     dword ptr [rax+rax+00h]
0x14007890d  lea     rax, [rdi+18h]
0x140078911  mov     rdx, [rax]
0x140078914  cmp     [rdx+8], rax
0x140078918  jnz     loc_140078A77
0x14007891e  mov     rcx, [rax+8]
0x140078922  cmp     [rcx], rax
0x140078925  jnz     loc_140078A77
0x14007892b  mov     [rcx], rdx
0x14007892e  mov     [rdx+8], rcx
0x140078932  mov     rax, [rsi+268h]
0x140078939  dec     dword ptr [rax+10h]
0x14007893c  mov     rcx, [rsi+268h]
0x140078943  add     rcx, 18h; Resource
0x140078947  call    cs:__imp_ExReleaseResourceLite
0x14007894e  nop     dword ptr [rax+rax+00h]
0x140078953  call    cs:__imp_KeLeaveCriticalRegion
0x14007895a  nop     dword ptr [rax+rax+00h]
0x14007895f  mov     rcx, [rdi+38h]; RunRef
0x140078963  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x14007896a  nop     dword ptr [rax+rax+00h]
0x14007896f  call    cs:__imp_KeEnterCriticalRegion
0x140078976  nop     dword ptr [rax+rax+00h]
0x14007897b  lea     r14, [rdi+180h]
0x140078982  mov     dl, 1; Wait
0x140078984  mov     rcx, r14; Resource
0x140078987  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14007898e  nop     dword ptr [rax+rax+00h]
0x140078993  cmp     dword ptr [rdi+178h], 0
0x14007899a  jbe     loc_140078A7E
0x1400789a0  lea     rbx, [rdi+168h]
0x1400789a7  mov     r8, [rbx]
0x1400789aa  cmp     r8, rbx
0x1400789ad  jz      loc_140078A7E
0x1400789b3  cmp     [r8+8], rbx
0x1400789b7  jnz     loc_140078A77
0x1400789bd  mov     rax, [r8]
0x1400789c0  cmp     [rax+8], r8
0x1400789c4  jnz     loc_140078A77
0x1400789ca  mov     [rbx], rax
0x1400789cd  lea     rbp, [r8-8]
0x1400789d1  mov     [rax+8], rbx
0x1400789d5  dec     dword ptr [rdi+178h]
0x1400789db  mov     rax, [rbp+20h]
0x1400789df  mov     [rsp+78h+arg_8], rbp
0x1400789e7  test    al, 10h
0x1400789e9  jnz     short loc_1400789A7
0x1400789eb  or      rax, 10h
0x1400789ef  mov     [rbp+20h], rax
0x1400789f3  test    cs:byte_14017743A, 4
0x1400789fa  jz      short loc_140078A50
0x1400789fc  lea     rax, [rbp+23Ch]
0x140078a03  mov     [rsp+78h+var_28], rax
0x140078a08  lea     rdx, [r8+134h]
0x140078a0f  movzx   eax, word ptr [rbp+4]
0x140078a13  lea     r9, [rdi+48h]
0x140078a17  mov     [rsp+78h+var_30], rdx
0x140078a1c  lea     r10, [rsi+418h]
0x140078a23  add     r8, 34h ; '4'
0x140078a27  mov     [rsp+78h+var_38], r8
0x140078a2c  mov     [rsp+78h+var_40], ax
0x140078a31  mov     rax, [rsi+408h]
0x140078a38  mov     [rsp+78h+var_48], r9
0x140078a3d  mov     r9d, [rsi+38h]
0x140078a41  mov     [rsp+78h+var_50], rax
0x140078a46  mov     [rsp+78h+var_58], r10
0x140078a4b  call    McTemplateK0qjzshsss_EtwWriteTransfer
0x140078a50  mov     rcx, [rbp+28h]; RunRef
0x140078a54  call    cs:__imp_ExWaitForRundownProtectionReleaseCacheAware
0x140078a5b  nop     dword ptr [rax+rax+00h]
0x140078a60  lea     r8, [rsp+78h+arg_8]
0x140078a68  mov     dl, 1
0x140078a6a  mov     rcx, rsi
0x140078a6d  call    NvmeAdapterCleanupSubsystemPort
0x140078a72  jmp     loc_1400789A7
0x140078a77  mov     ecx, 3
0x140078a7c  int     29h; Win8: RtlFailFast(ecx)
0x140078a7e  mov     rcx, r14; Resource
0x140078a81  xor     ebx, ebx
0x140078a83  call    cs:__imp_ExReleaseResourceLite
0x140078a8a  nop     dword ptr [rax+rax+00h]
0x140078a8f  call    cs:__imp_KeLeaveCriticalRegion
0x140078a96  nop     dword ptr [rax+rax+00h]
0x140078a9b  mov     rcx, r14; Resource
0x140078a9e  call    cs:__imp_ExDeleteResourceLite
0x140078aa5  nop     dword ptr [rax+rax+00h]
0x140078aaa  mov     rcx, [rdi+38h]; RunRefCacheAware
0x140078aae  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140078ab5  nop     dword ptr [rax+rax+00h]
0x140078aba  test    cs:byte_14017743A, 4
0x140078ac1  jz      short loc_140078B0E
0x140078ac3  mov     r9d, [rsi+38h]
0x140078ac7  lea     rax, [rdi+148h]
0x140078ace  mov     [rsp+78h+var_30], rax
0x140078ad3  lea     rcx, [rdi+48h]
0x140078ad7  mov     al, [rdi+8]
0x140078ada  lea     rdx, [rsi+418h]
0x140078ae1  mov     [rsp+78h+var_38], rcx
0x140078ae6  mov     byte ptr [rsp+78h+var_40], al
0x140078aea  mov     al, [rdi+4]
0x140078aed  mov     byte ptr [rsp+78h+var_48], al
0x140078af1  mov     rax, [rsi+408h]
0x140078af8  mov     [rsp+78h+var_50], rax
0x140078afd  mov     [rsp+78h+var_58], rdx
0x140078b02  lea     rdx, EventNVMeoFHostGatewayRemoved
0x140078b09  call    McTemplateK0qjzuuss_EtwWriteTransfer
0x140078b0e  mov     edx, 464E6152h; Tag
0x140078b13  mov     rcx, rdi; P
0x140078b16  call    cs:__imp_ExFreePoolWithTag
0x140078b1d  nop     dword ptr [rax+rax+00h]
0x140078b22  jmp     short loc_140078B29
0x140078b24  mov     ebx, 0C00000BBh
0x140078b29  lea     r11, [rsp+78h+var_18]
0x140078b2e  mov     eax, ebx
0x140078b30  mov     rbx, [r11+20h]
0x140078b34  mov     rbp, [r11+30h]
0x140078b38  mov     rsp, r11
0x140078b3b  pop     r14
0x140078b3d  pop     rdi
0x140078b3e  pop     rsi
0x140078b3f  retn
```

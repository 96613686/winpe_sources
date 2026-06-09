# WimBootEnvironmentDeviceToPath

- ea: `0x14002b0f0`
- end: `0x14002b335`
- name: `WimBootEnvironmentDeviceToPath`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002d424`

## callees

- `0x14000d3b8`
- `0x140010078`
- `0x14002b0f0`
- `0x14002f254`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002b294`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002b2a7`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002b294`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002b2a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b12b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b315`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b12b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b315`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b142`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b233`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b142`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b233`

## pseudocode

```c
__int64 __fastcall WimBootEnvironmentDeviceToPath(__int64 a1, struct _UNICODE_STRING *a2)
{
  WCHAR *v4; // rbx
  unsigned int i; // edi
  WCHAR *PoolWithTag; // rax
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // r9
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  const WCHAR *v13; // rbp
  __int64 v14; // rax
  __int64 v15; // rdx
  USHORT v16; // r15
  WCHAR *v17; // rax
  int v19; // [rsp+90h] [rbp+18h] BYREF

  v19 = 1024;
  v4 = 0;
  for ( i = 1024; ; i = v19 )
  {
    if ( v4 )
      ExFreePoolWithTag(v4, 0);
    PoolWithTag = (WCHAR *)ExAllocatePoolWithTag(PagedPool, i, 0x66637077u);
    v4 = PoolWithTag;
    if ( !PoolWithTag )
    {
      v8 = -1073741801;
      goto LABEL_29;
    }
    v7 = BcdConvertBootEnvironmentDeviceToElement(a1, PoolWithTag, &v19);
    v8 = v7;
    if ( v7 != -1073741789 )
      break;
  }
  if ( v7 >= 0 )
  {
    v9 = *(unsigned int *)v4;
    if ( (_DWORD)v9 != 3 )
    {
      v8 = -1073741621;
      v10 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v11 = 40;
        goto LABEL_12;
      }
      goto LABEL_33;
    }
    v12 = *((unsigned int *)v4 + 5);
    v9 = *(unsigned int *)((char *)v4 + v12);
    if ( (_DWORD)v9 == 2 )
    {
      v13 = (WCHAR *)((char *)v4 + v12 + 20);
    }
    else
    {
      if ( (_DWORD)v9 != 5 )
      {
        v8 = -1073741621;
        v10 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v11 = 41;
LABEL_12:
          WPP_SF_dd(v10->AttachedDevice, v11, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, v9, -1073741621);
        }
LABEL_33:
        ExFreePoolWithTag(v4, 0);
        return v8;
      }
      v13 = L"\\Device\\HarddiskVolumeUnknown";
    }
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( v4[v15 + 12] );
    do
      ++v14;
    while ( v13[v14] );
    v16 = 2 * (v15 + v14 + 1);
    v17 = (WCHAR *)ExAllocatePoolWithTag(PagedPool, v16, 0x66637077u);
    if ( v17 )
    {
      *a2 = 0;
      a2->MaximumLength = v16;
      a2->Buffer = v17;
      RtlAppendUnicodeToString(a2, v13);
      RtlAppendUnicodeToString(a2, v4 + 12);
    }
    else
    {
      v8 = -1073741670;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, 3221225626LL);
    }
    goto LABEL_33;
  }
LABEL_29:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids, v8);
  if ( v4 )
    goto LABEL_33;
  return v8;
}

```

## disassembly

```asm
0x14002b0f0  mov     rax, rsp
0x14002b0f3  push    rbx
0x14002b0f4  push    rbp
0x14002b0f5  push    rsi
0x14002b0f6  push    rdi
0x14002b0f7  push    r12
0x14002b0f9  push    r13
0x14002b0fb  push    r14
0x14002b0fd  push    r15
0x14002b0ff  sub     rsp, 38h
0x14002b103  xor     r12d, r12d
0x14002b106  mov     r13d, 400h
0x14002b10c  mov     rsi, rdx
0x14002b10f  mov     [rax+18h], r13d
0x14002b113  mov     rbp, rcx
0x14002b116  mov     ebx, r12d
0x14002b119  mov     edi, r13d
0x14002b11c  lea     r15d, [r12+1]
0x14002b121  test    rbx, rbx
0x14002b124  jz      short loc_14002B137
0x14002b126  xor     edx, edx; Tag
0x14002b128  mov     rcx, rbx; P
0x14002b12b  call    cs:__imp_ExFreePoolWithTag
0x14002b132  nop     dword ptr [rax+rax+00h]
0x14002b137  mov     edx, edi; NumberOfBytes
0x14002b139  mov     r8d, 66637077h; Tag
0x14002b13f  mov     ecx, r15d; PoolType
0x14002b142  call    cs:__imp_ExAllocatePoolWithTag
0x14002b149  nop     dword ptr [rax+rax+00h]
0x14002b14e  mov     rbx, rax
0x14002b151  test    rax, rax
0x14002b154  jz      loc_14002B2DB
0x14002b15a  lea     r8, [rsp+78h+arg_10]
0x14002b162  mov     rdx, rax
0x14002b165  mov     rcx, rbp
0x14002b168  call    BcdConvertBootEnvironmentDeviceToElement
0x14002b16d  mov     edi, eax
0x14002b16f  cmp     eax, 0C0000023h
0x14002b174  jnz     short loc_14002B17F
0x14002b176  mov     edi, [rsp+78h+arg_10]
0x14002b17d  jmp     short loc_14002B121
0x14002b17f  test    eax, eax
0x14002b181  js      loc_14002B2E0
0x14002b187  mov     r9d, [rbx]
0x14002b18a  cmp     r9d, 3
0x14002b18e  jz      short loc_14002B1D3
0x14002b190  mov     r8d, 0C00000CBh
0x14002b196  mov     edi, r8d
0x14002b199  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b1a0  test    [rcx+2Ch], r13d
0x14002b1a4  jz      loc_14002B310
0x14002b1aa  cmp     byte ptr [rcx+29h], 2
0x14002b1ae  jb      loc_14002B310
0x14002b1b4  mov     edx, 28h ; '('
0x14002b1b9  mov     rcx, [rcx+18h]
0x14002b1bd  mov     [rsp+78h+var_58], r8d
0x14002b1c2  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002b1c9  call    WPP_SF_dd
0x14002b1ce  jmp     loc_14002B310
0x14002b1d3  mov     eax, [rbx+14h]
0x14002b1d6  mov     r9d, [rax+rbx]
0x14002b1da  cmp     r9d, 2
0x14002b1de  jnz     short loc_14002B1E9
0x14002b1e0  lea     rbp, [rbx+14h]
0x14002b1e4  add     rbp, rax
0x14002b1e7  jmp     short loc_14002B1FA
0x14002b1e9  cmp     r9d, 5
0x14002b1ed  jnz     loc_14002B2B5
0x14002b1f3  lea     rbp, aDeviceHarddisk_2; "\\Device\\HarddiskVolumeUnknown"
0x14002b1fa  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002b1fe  mov     rdx, rax
0x14002b201  inc     rdx
0x14002b204  cmp     [rbx+rdx*2+18h], r12w
0x14002b20a  jnz     short loc_14002B201
0x14002b20c  inc     rax
0x14002b20f  cmp     [rbp+rax*2+0], r12w
0x14002b215  jnz     short loc_14002B20C
0x14002b217  add     ax, dx
0x14002b21a  mov     ecx, 1; PoolType
0x14002b21f  add     ax, r15w
0x14002b223  mov     r8d, 66637077h; Tag
0x14002b229  add     ax, ax
0x14002b22c  movzx   r15d, ax
0x14002b230  mov     edx, r15d; NumberOfBytes
0x14002b233  call    cs:__imp_ExAllocatePoolWithTag
0x14002b23a  nop     dword ptr [rax+rax+00h]
0x14002b23f  test    rax, rax
0x14002b242  jnz     short loc_14002B27F
0x14002b244  mov     edi, 0C000009Ah
0x14002b249  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b250  test    [rcx+2Ch], r13d
0x14002b254  jz      loc_14002B310
0x14002b25a  cmp     byte ptr [rcx+29h], 2
0x14002b25e  jb      loc_14002B310
0x14002b264  mov     rcx, [rcx+18h]
0x14002b268  lea     edx, [rax+2Ah]
0x14002b26b  mov     r9d, edi
0x14002b26e  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002b275  call    WPP_SF_d
0x14002b27a  jmp     loc_14002B310
0x14002b27f  xorps   xmm0, xmm0
0x14002b282  mov     rdx, rbp; Source
0x14002b285  movups  xmmword ptr [rsi], xmm0
0x14002b288  mov     rcx, rsi; Destination
0x14002b28b  mov     [rsi+2], r15w
0x14002b290  mov     [rsi+8], rax
0x14002b294  call    cs:__imp_RtlAppendUnicodeToString
0x14002b29b  nop     dword ptr [rax+rax+00h]
0x14002b2a0  lea     rdx, [rbx+18h]; Source
0x14002b2a4  mov     rcx, rsi; Destination
0x14002b2a7  call    cs:__imp_RtlAppendUnicodeToString
0x14002b2ae  nop     dword ptr [rax+rax+00h]
0x14002b2b3  jmp     short loc_14002B310
0x14002b2b5  mov     r8d, 0C00000CBh
0x14002b2bb  mov     edi, r8d
0x14002b2be  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b2c5  test    [rcx+2Ch], r13d
0x14002b2c9  jz      short loc_14002B310
0x14002b2cb  cmp     byte ptr [rcx+29h], 2
0x14002b2cf  jb      short loc_14002B310
0x14002b2d1  mov     edx, 29h ; ')'
0x14002b2d6  jmp     loc_14002B1B9
0x14002b2db  mov     edi, 0C0000017h
0x14002b2e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b2e7  test    [rcx+2Ch], r13d
0x14002b2eb  jz      short loc_14002B30B
0x14002b2ed  cmp     byte ptr [rcx+29h], 2
0x14002b2f1  jb      short loc_14002B30B
0x14002b2f3  mov     rcx, [rcx+18h]
0x14002b2f7  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002b2fe  mov     edx, 27h ; '''
0x14002b303  mov     r9d, edi
0x14002b306  call    WPP_SF_d
0x14002b30b  test    rbx, rbx
0x14002b30e  jz      short loc_14002B321
0x14002b310  xor     edx, edx; Tag
0x14002b312  mov     rcx, rbx; P
0x14002b315  call    cs:__imp_ExFreePoolWithTag
0x14002b31c  nop     dword ptr [rax+rax+00h]
0x14002b321  mov     eax, edi
0x14002b323  add     rsp, 38h
0x14002b327  pop     r15
0x14002b329  pop     r14
0x14002b32b  pop     r13
0x14002b32d  pop     r12
0x14002b32f  pop     rdi
0x14002b330  pop     rsi
0x14002b331  pop     rbp
0x14002b332  pop     rbx
0x14002b333  retn
```

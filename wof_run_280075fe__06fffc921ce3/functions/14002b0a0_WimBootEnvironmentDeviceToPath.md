# WimBootEnvironmentDeviceToPath

- ea: `0x14002b0a0`
- end: `0x14002b2e5`
- name: `WimBootEnvironmentDeviceToPath`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002d3d4`

## callees

- `0x14000d3b8`
- `0x140010078`
- `0x14002b0a0`
- `0x14002f204`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002b244`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002b257`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002b244`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14002b257`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b0db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b2c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b0db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b2c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b0f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b1e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b0f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b1e3`

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
0x14002b0a0  mov     rax, rsp
0x14002b0a3  push    rbx
0x14002b0a4  push    rbp
0x14002b0a5  push    rsi
0x14002b0a6  push    rdi
0x14002b0a7  push    r12
0x14002b0a9  push    r13
0x14002b0ab  push    r14
0x14002b0ad  push    r15
0x14002b0af  sub     rsp, 38h
0x14002b0b3  xor     r12d, r12d
0x14002b0b6  mov     r13d, 400h
0x14002b0bc  mov     rsi, rdx
0x14002b0bf  mov     [rax+18h], r13d
0x14002b0c3  mov     rbp, rcx
0x14002b0c6  mov     ebx, r12d
0x14002b0c9  mov     edi, r13d
0x14002b0cc  lea     r15d, [r12+1]
0x14002b0d1  test    rbx, rbx
0x14002b0d4  jz      short loc_14002B0E7
0x14002b0d6  xor     edx, edx; Tag
0x14002b0d8  mov     rcx, rbx; P
0x14002b0db  call    cs:__imp_ExFreePoolWithTag
0x14002b0e2  nop     dword ptr [rax+rax+00h]
0x14002b0e7  mov     edx, edi; NumberOfBytes
0x14002b0e9  mov     r8d, 66637077h; Tag
0x14002b0ef  mov     ecx, r15d; PoolType
0x14002b0f2  call    cs:__imp_ExAllocatePoolWithTag
0x14002b0f9  nop     dword ptr [rax+rax+00h]
0x14002b0fe  mov     rbx, rax
0x14002b101  test    rax, rax
0x14002b104  jz      loc_14002B28B
0x14002b10a  lea     r8, [rsp+78h+arg_10]
0x14002b112  mov     rdx, rax
0x14002b115  mov     rcx, rbp
0x14002b118  call    BcdConvertBootEnvironmentDeviceToElement
0x14002b11d  mov     edi, eax
0x14002b11f  cmp     eax, 0C0000023h
0x14002b124  jnz     short loc_14002B12F
0x14002b126  mov     edi, [rsp+78h+arg_10]
0x14002b12d  jmp     short loc_14002B0D1
0x14002b12f  test    eax, eax
0x14002b131  js      loc_14002B290
0x14002b137  mov     r9d, [rbx]
0x14002b13a  cmp     r9d, 3
0x14002b13e  jz      short loc_14002B183
0x14002b140  mov     r8d, 0C00000CBh
0x14002b146  mov     edi, r8d
0x14002b149  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b150  test    [rcx+2Ch], r13d
0x14002b154  jz      loc_14002B2C0
0x14002b15a  cmp     byte ptr [rcx+29h], 2
0x14002b15e  jb      loc_14002B2C0
0x14002b164  mov     edx, 28h ; '('
0x14002b169  mov     rcx, [rcx+18h]
0x14002b16d  mov     [rsp+78h+var_58], r8d
0x14002b172  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002b179  call    WPP_SF_dd
0x14002b17e  jmp     loc_14002B2C0
0x14002b183  mov     eax, [rbx+14h]
0x14002b186  mov     r9d, [rax+rbx]
0x14002b18a  cmp     r9d, 2
0x14002b18e  jnz     short loc_14002B199
0x14002b190  lea     rbp, [rbx+14h]
0x14002b194  add     rbp, rax
0x14002b197  jmp     short loc_14002B1AA
0x14002b199  cmp     r9d, 5
0x14002b19d  jnz     loc_14002B265
0x14002b1a3  lea     rbp, aDeviceHarddisk_2; "\\Device\\HarddiskVolumeUnknown"
0x14002b1aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002b1ae  mov     rdx, rax
0x14002b1b1  inc     rdx
0x14002b1b4  cmp     [rbx+rdx*2+18h], r12w
0x14002b1ba  jnz     short loc_14002B1B1
0x14002b1bc  inc     rax
0x14002b1bf  cmp     [rbp+rax*2+0], r12w
0x14002b1c5  jnz     short loc_14002B1BC
0x14002b1c7  add     ax, dx
0x14002b1ca  mov     ecx, 1; PoolType
0x14002b1cf  add     ax, r15w
0x14002b1d3  mov     r8d, 66637077h; Tag
0x14002b1d9  add     ax, ax
0x14002b1dc  movzx   r15d, ax
0x14002b1e0  mov     edx, r15d; NumberOfBytes
0x14002b1e3  call    cs:__imp_ExAllocatePoolWithTag
0x14002b1ea  nop     dword ptr [rax+rax+00h]
0x14002b1ef  test    rax, rax
0x14002b1f2  jnz     short loc_14002B22F
0x14002b1f4  mov     edi, 0C000009Ah
0x14002b1f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b200  test    [rcx+2Ch], r13d
0x14002b204  jz      loc_14002B2C0
0x14002b20a  cmp     byte ptr [rcx+29h], 2
0x14002b20e  jb      loc_14002B2C0
0x14002b214  mov     rcx, [rcx+18h]
0x14002b218  lea     edx, [rax+2Ah]
0x14002b21b  mov     r9d, edi
0x14002b21e  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002b225  call    WPP_SF_d
0x14002b22a  jmp     loc_14002B2C0
0x14002b22f  xorps   xmm0, xmm0
0x14002b232  mov     rdx, rbp; Source
0x14002b235  movups  xmmword ptr [rsi], xmm0
0x14002b238  mov     rcx, rsi; Destination
0x14002b23b  mov     [rsi+2], r15w
0x14002b240  mov     [rsi+8], rax
0x14002b244  call    cs:__imp_RtlAppendUnicodeToString
0x14002b24b  nop     dword ptr [rax+rax+00h]
0x14002b250  lea     rdx, [rbx+18h]; Source
0x14002b254  mov     rcx, rsi; Destination
0x14002b257  call    cs:__imp_RtlAppendUnicodeToString
0x14002b25e  nop     dword ptr [rax+rax+00h]
0x14002b263  jmp     short loc_14002B2C0
0x14002b265  mov     r8d, 0C00000CBh
0x14002b26b  mov     edi, r8d
0x14002b26e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b275  test    [rcx+2Ch], r13d
0x14002b279  jz      short loc_14002B2C0
0x14002b27b  cmp     byte ptr [rcx+29h], 2
0x14002b27f  jb      short loc_14002B2C0
0x14002b281  mov     edx, 29h ; ')'
0x14002b286  jmp     loc_14002B169
0x14002b28b  mov     edi, 0C0000017h
0x14002b290  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b297  test    [rcx+2Ch], r13d
0x14002b29b  jz      short loc_14002B2BB
0x14002b29d  cmp     byte ptr [rcx+29h], 2
0x14002b2a1  jb      short loc_14002B2BB
0x14002b2a3  mov     rcx, [rcx+18h]
0x14002b2a7  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002b2ae  mov     edx, 27h ; '''
0x14002b2b3  mov     r9d, edi
0x14002b2b6  call    WPP_SF_d
0x14002b2bb  test    rbx, rbx
0x14002b2be  jz      short loc_14002B2D1
0x14002b2c0  xor     edx, edx; Tag
0x14002b2c2  mov     rcx, rbx; P
0x14002b2c5  call    cs:__imp_ExFreePoolWithTag
0x14002b2cc  nop     dword ptr [rax+rax+00h]
0x14002b2d1  mov     eax, edi
0x14002b2d3  add     rsp, 38h
0x14002b2d7  pop     r15
0x14002b2d9  pop     r14
0x14002b2db  pop     r13
0x14002b2dd  pop     r12
0x14002b2df  pop     rdi
0x14002b2e0  pop     rsi
0x14002b2e1  pop     rbp
0x14002b2e2  pop     rbx
0x14002b2e3  retn
```

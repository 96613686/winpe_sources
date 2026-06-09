# UdfGetVolumeBitmap

- ea: `0x140010f38`
- end: `0x14001126a`
- name: `UdfGetVolumeBitmap`
- size: `818`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14004b594`

## callees

- `0x1400030e0`
- `0x14000c21c`
- `0x14000e5d8`
- `0x140010cb0`
- `0x140010f38`
- `0x14004ce50`
- `0x1400543e0`
- `0x140054460`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140011223`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001123d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d928`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d946`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011223`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001123d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d928`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d946`
- `ntoskrnl!ProbeForRead` at `0x14001100a`
- `ntoskrnl!ProbeForRead` at `0x14001100a`
- `ntoskrnl!ProbeForWrite` at `0x140011026`
- `ntoskrnl!ProbeForWrite` at `0x140011026`

## pseudocode

```c
__int64 __fastcall UdfGetVolumeBitmap(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rcx
  SIZE_T v6; // r13
  unsigned int v7; // r12d
  __int64 v8; // rdi
  bool v9; // r14
  __int64 v10; // rcx
  unsigned int v11; // ebx
  _QWORD *v12; // r12
  unsigned int v13; // edx
  unsigned int v14; // r14d
  unsigned int v15; // r13d
  unsigned int v16; // eax
  unsigned int v17; // r12d
  unsigned int v18; // eax
  _BYTE *v19; // rdx
  unsigned int v20; // r8d
  _BYTE *v21; // r9
  char v23; // [rsp+20h] [rbp-78h]
  char v24; // [rsp+21h] [rbp-77h]
  __int64 v25; // [rsp+30h] [rbp-68h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-60h]
  unsigned int v27; // [rsp+3Ch] [rbp-5Ch]
  int v28; // [rsp+40h] [rbp-58h]
  _BYTE *v29; // [rsp+48h] [rbp-50h]
  _BYTE *v30; // [rsp+50h] [rbp-48h]
  __int64 v31; // [rsp+58h] [rbp-40h] BYREF
  unsigned int Length; // [rsp+B8h] [rbp+20h]

  v4 = *(_QWORD *)(a2 + 184);
  v5 = *(_QWORD *)(v4 + 48);
  v6 = *(unsigned int *)(v4 + 16);
  v7 = *(_DWORD *)(v4 + 8);
  Length = v7;
  v8 = *(_QWORD *)(a1 + 16);
  v26 = *(_DWORD *)(v8 + 664);
  v9 = *(_BYTE *)(a2 + 64) == 0;
  *(_DWORD *)(a1 + 28) |= 4u;
  v24 = 0;
  v23 = 0;
  if ( (unsigned int)UdfDecodeFileObject(v5, &v31, &v25) != 2 )
  {
LABEL_2:
    v11 = -1073741811;
    goto LABEL_26;
  }
  if ( !(unsigned int)Feature_Udfs_Bitmap_Dismount__private_IsEnabledDeviceUsageNoInline()
    && (*(_DWORD *)(v8 + 48) & 0x40) == 0 )
  {
    goto LABEL_5;
  }
  if ( (unsigned int)v6 < 8 || v7 < 0x18 )
  {
    v11 = -1073741789;
  }
  else
  {
    v12 = (_QWORD *)UdfMapUserBuffer(a1, a2);
    if ( !v9 )
    {
      ProbeForRead(*(volatile void **)(v4 + 32), v6, 1u);
      ProbeForWrite(v12, Length, 1u);
    }
    v25 = **(_QWORD **)(v4 + 32);
    if ( HIDWORD(v25) )
      goto LABEL_2;
    v13 = v26;
    if ( (unsigned int)v25 >= v26 )
      goto LABEL_2;
    LODWORD(v25) = v25 & 0xFFFFFFF8;
    v14 = v25;
    *v12 = v25;
    v12[1] = v13 - v14;
    v29 = v12 + 2;
    v15 = 16;
    v28 = 16;
    v16 = (((v13 + 7) & 0xFFFFFFF8) - v14) >> 3;
    v17 = v16;
    if ( v16 > Length - 16 )
      v17 = Length - 16;
    v11 = Length - 16 < v16 ? 0x80000005 : 0;
    UdfAcquireResource(a1, v8 + 1480, 0, 1);
    v24 = 1;
    if ( (unsigned int)Feature_Udfs_Bitmap_Dismount__private_IsEnabledDeviceUsageNoInline()
      && (*(_DWORD *)(v8 + 48) & 0x40) == 0 )
    {
LABEL_5:
      v11 = -1073741808;
      goto LABEL_26;
    }
    UdfAcquireResource(a1, v8 + 552, 0, 0);
    v23 = 1;
    while ( v17 )
    {
      UdfMapOrPinBitmapLbnRange(a1, 0, v14);
      v18 = (v14 - *(_DWORD *)(v8 + 520)) >> 3;
      v10 = (*(_DWORD *)(v8 + 524) >> 3) - v18;
      if ( (unsigned int)v10 > v17 )
        v10 = v17;
      v19 = (_BYTE *)(*(_QWORD *)(v8 + 512) + v18);
      v30 = v19;
      v20 = 0;
      v27 = 0;
      v21 = v29;
      while ( v20 < (unsigned int)v10 )
      {
        *v21++ = ~*v19;
        v29 = v21;
        v30 = ++v19;
        v27 = ++v20;
      }
      v15 += v10;
      v28 = v15;
      v17 -= v10;
      v14 += 8 * v10;
      LODWORD(v25) = v14;
    }
    *(_QWORD *)(a2 + 56) = v15;
  }
LABEL_26:
  if ( v23 )
  {
    UdfUnpinCurrentBitmapPage(v10, v8, 0);
    ExReleaseResourceLite((PERESOURCE)(v8 + 552));
  }
  if ( v24 )
    ExReleaseResourceLite((PERESOURCE)(v8 + 1480));
  UdfCompleteRequest(a1, a2, v11);
  return v11;
}

```

## disassembly

```asm
0x140010f38  mov     r11, rsp
0x140010f3b  mov     [r11+10h], rdx
0x140010f3f  mov     [r11+8], rcx
0x140010f43  push    rbx
0x140010f44  push    rsi
0x140010f45  push    rdi
0x140010f46  push    r12
0x140010f48  push    r13
0x140010f4a  push    r14
0x140010f4c  push    r15
0x140010f4e  sub     rsp, 60h
0x140010f52  mov     r15, rdx
0x140010f55  mov     rsi, rcx
0x140010f58  mov     rbx, [rdx+0B8h]
0x140010f5f  mov     rcx, [rbx+30h]
0x140010f63  mov     r13d, [rbx+10h]
0x140010f67  mov     r12d, [rbx+8]
0x140010f6b  mov     [r11+20h], r12d
0x140010f6f  mov     rdi, [rsi+10h]
0x140010f73  mov     [rsp+98h+var_70], rdi
0x140010f78  mov     eax, [rdi+298h]
0x140010f7e  mov     [rsp+98h+var_60], eax
0x140010f82  cmp     byte ptr [rdx+40h], 0
0x140010f86  setz    r14b
0x140010f8a  mov     [rsp+98h+arg_10], r14b
0x140010f92  or      dword ptr [rsi+1Ch], 4
0x140010f96  mov     [rsp+98h+var_77], 0
0x140010f9b  mov     [rsp+98h+var_78], 0
0x140010fa0  lea     r8, [r11-68h]
0x140010fa4  lea     rdx, [r11-40h]
0x140010fa8  call    UdfDecodeFileObject
0x140010fad  cmp     eax, 2
0x140010fb0  jz      short loc_140010FBC
0x140010fb2  mov     ebx, 0C000000Dh
0x140010fb7  jmp     loc_14001120A
0x140010fbc  call    Feature_Udfs_Bitmap_Dismount__private_IsEnabledDeviceUsageNoInline
0x140010fc1  test    eax, eax
0x140010fc3  jnz     short loc_140010FD6
0x140010fc5  mov     eax, [rdi+30h]
0x140010fc8  test    al, 40h
0x140010fca  jnz     short loc_140010FD6
0x140010fcc  mov     ebx, 0C0000010h
0x140010fd1  jmp     loc_14001120A
0x140010fd6  cmp     r13d, 8
0x140010fda  jb      loc_140011205
0x140010fe0  cmp     r12d, 18h
0x140010fe4  jb      loc_140011205
0x140010fea  mov     rdx, r15
0x140010fed  mov     rcx, rsi
0x140010ff0  call    UdfMapUserBuffer
0x140010ff5  mov     r12, rax
0x140010ff8  test    r14b, r14b
0x140010ffb  jnz     short loc_140011032
0x140010ffd  mov     rdx, r13; Length
0x140011000  mov     r8d, 1; Alignment
0x140011006  mov     rcx, [rbx+20h]; Address
0x14001100a  call    cs:__imp_ProbeForRead
0x140011011  nop     dword ptr [rax+rax+00h]
0x140011016  mov     edx, dword ptr [rsp+98h+Length]; Length
0x14001101d  mov     r8d, 1; Alignment
0x140011023  mov     rcx, r12; Address
0x140011026  call    cs:__imp_ProbeForWrite
0x14001102d  nop     dword ptr [rax+rax+00h]
0x140011032  mov     rax, [rbx+20h]
0x140011036  mov     rax, [rax]
0x140011039  mov     [rsp+98h+var_68], rax
0x14001103e  shr     rax, 20h
0x140011042  test    eax, eax
0x140011044  jnz     loc_140010FB2
0x14001104a  mov     r14d, dword ptr [rsp+98h+var_68]
0x14001104f  mov     edx, [rsp+98h+var_60]
0x140011053  cmp     r14d, edx
0x140011056  jnb     loc_140010FB2
0x14001105c  mov     r8d, 0FFFFFFF8h
0x140011062  and     r14d, r8d
0x140011065  mov     dword ptr [rsp+98h+var_68], r14d
0x14001106a  mov     rax, [rsp+98h+var_68]
0x14001106f  mov     [r12], rax
0x140011073  mov     eax, edx
0x140011075  sub     eax, r14d
0x140011078  mov     [r12+8], rax
0x14001107d  lea     rax, [r12+10h]
0x140011082  mov     [rsp+98h+var_50], rax
0x140011087  mov     r13d, 10h
0x14001108d  mov     [rsp+98h+var_58], r13d
0x140011092  mov     ecx, dword ptr [rsp+98h+Length]
0x140011099  add     ecx, 0FFFFFFF0h
0x14001109c  lea     eax, [rdx+7]
0x14001109f  and     eax, r8d
0x1400110a2  sub     eax, r14d
0x1400110a5  shr     eax, 3
0x1400110a8  mov     [rsp+98h+var_74], eax
0x1400110ac  mov     r12d, eax
0x1400110af  cmp     eax, ecx
0x1400110b1  cmova   r12d, ecx
0x1400110b5  mov     [rsp+98h+var_74], r12d
0x1400110ba  cmp     ecx, eax
0x1400110bc  sbb     ebx, ebx
0x1400110be  and     ebx, 80000005h
0x1400110c4  lea     rdx, [rdi+5C8h]
0x1400110cb  lea     r9d, [r13-0Fh]
0x1400110cf  xor     r8d, r8d
0x1400110d2  mov     rcx, rsi
0x1400110d5  call    UdfAcquireResource
0x1400110da  mov     [rsp+98h+var_77], 1
0x1400110df  call    Feature_Udfs_Bitmap_Dismount__private_IsEnabledDeviceUsageNoInline
0x1400110e4  test    eax, eax
0x1400110e6  jz      short loc_1400110F3
0x1400110e8  mov     eax, [rdi+30h]
0x1400110eb  test    al, 40h
0x1400110ed  jz      loc_140010FCC
0x1400110f3  lea     rdx, [rdi+228h]
0x1400110fa  xor     r9d, r9d
0x1400110fd  xor     r8d, r8d
0x140011100  mov     rcx, rsi
0x140011103  call    UdfAcquireResource
0x140011108  mov     [rsp+98h+var_78], 1
0x14001110d  test    r12d, r12d
0x140011110  jz      loc_1400111C4
0x140011116  mov     r8d, r14d
0x140011119  xor     edx, edx
0x14001111b  mov     rcx, rsi
0x14001111e  call    UdfMapOrPinBitmapLbnRange
0x140011123  mov     eax, r14d
0x140011126  sub     eax, [rdi+208h]
0x14001112c  shr     eax, 3
0x14001112f  mov     edx, eax
0x140011131  mov     ecx, [rdi+20Ch]
0x140011137  shr     ecx, 3
0x14001113a  sub     ecx, eax
0x14001113c  cmp     ecx, r12d
0x14001113f  cmova   ecx, r12d
0x140011143  mov     rax, [rdi+200h]
0x14001114a  mov     [rsp+98h+var_48], rax
0x14001114f  add     rdx, rax
0x140011152  mov     [rsp+98h+var_48], rdx
0x140011157  xor     r8d, r8d
0x14001115a  mov     [rsp+98h+var_5C], r8d
0x14001115f  mov     r9, [rsp+98h+var_50]
0x140011164  cmp     r8d, ecx
0x140011167  jnb     short loc_1400111A6
0x140011169  mov     al, [rdx]
0x14001116b  not     al
0x14001116d  mov     [r9], al
0x140011170  inc     r9
0x140011173  mov     [rsp+98h+var_50], r9
0x140011178  inc     rdx
0x14001117b  mov     [rsp+98h+var_48], rdx
0x140011180  inc     r8d
0x140011183  mov     [rsp+98h+var_5C], r8d
0x140011188  jmp     short loc_140011164
0x14001118a  mov     ebx, 0C00000E8h
0x14001118f  mov     r15, [rsp+98h+arg_8]
0x140011197  mov     rsi, [rsp+98h+arg_0]
0x14001119f  mov     rdi, [rsp+98h+var_70]
0x1400111a4  jmp     short loc_14001120A
0x1400111a6  add     r13d, ecx
0x1400111a9  mov     [rsp+98h+var_58], r13d
0x1400111ae  sub     r12d, ecx
0x1400111b1  mov     [rsp+98h+var_74], r12d
0x1400111b6  lea     r14d, [r14+rcx*8]
0x1400111ba  mov     dword ptr [rsp+98h+var_68], r14d
0x1400111bf  jmp     loc_14001110D
0x1400111c4  mov     eax, r13d
0x1400111c7  mov     [r15+38h], rax
0x1400111cb  jmp     short loc_14001120A
0x1400111cd  mov     ebx, 0C00000E8h
0x1400111d2  mov     r15, [rsp+98h+arg_8]
0x1400111da  mov     rsi, [rsp+98h+arg_0]
0x1400111e2  mov     rdi, [rsp+98h+var_70]
0x1400111e7  jmp     short loc_14001120A
0x1400111e9  mov     ebx, 0C00000E8h
0x1400111ee  mov     r15, [rsp+98h+arg_8]
0x1400111f6  mov     rsi, [rsp+98h+arg_0]
0x1400111fe  mov     rdi, [rsp+98h+var_70]
0x140011203  jmp     short loc_14001120A
0x140011205  mov     ebx, 0C0000023h
0x14001120a  cmp     [rsp+98h+var_78], 0
0x14001120f  jz      short loc_14001122F
0x140011211  xor     r8d, r8d
0x140011214  mov     rdx, rdi
0x140011217  call    UdfUnpinCurrentBitmapPage
0x14001121c  lea     rcx, [rdi+228h]; Resource
0x140011223  call    cs:__imp_ExReleaseResourceLite
0x14001122a  nop     dword ptr [rax+rax+00h]
0x14001122f  cmp     [rsp+98h+var_77], 0
0x140011234  jz      short loc_140011249
0x140011236  lea     rcx, [rdi+5C8h]; Resource
0x14001123d  call    cs:__imp_ExReleaseResourceLite
0x140011244  nop     dword ptr [rax+rax+00h]
0x140011249  mov     r8d, ebx
0x14001124c  mov     rdx, r15
0x14001124f  mov     rcx, rsi
0x140011252  call    UdfCompleteRequest
0x140011257  mov     eax, ebx
0x140011259  add     rsp, 60h
0x14001125d  pop     r15
0x14001125f  pop     r14
0x140011261  pop     r13
0x140011263  pop     r12
0x140011265  pop     rdi
0x140011266  pop     rsi
0x140011267  pop     rbx
0x140011268  retn
0x14001d8b1  push    rbp
0x14001d8b3  sub     rsp, 20h
0x14001d8b7  mov     rbp, rdx
0x14001d8ba  xor     eax, eax
0x14001d8bc  cmp     [rbp+0B0h], al
0x14001d8c2  setz    al
0x14001d8c5  add     rsp, 20h
0x14001d8c9  pop     rbp
0x14001d8ca  retn
0x14001d8cc  push    rbp
0x14001d8ce  sub     rsp, 20h
0x14001d8d2  mov     rbp, rdx
0x14001d8d5  xor     eax, eax
0x14001d8d7  cmp     [rbp+0B0h], al
0x14001d8dd  setz    al
0x14001d8e0  add     rsp, 20h
0x14001d8e4  pop     rbp
0x14001d8e5  retn
0x14001d8e7  push    rbp
0x14001d8e9  sub     rsp, 20h
0x14001d8ed  mov     rbp, rdx
0x14001d8f0  xor     eax, eax
0x14001d8f2  cmp     [rbp+0B0h], al
0x14001d8f8  setz    al
0x14001d8fb  add     rsp, 20h
0x14001d8ff  pop     rbp
0x14001d900  retn
0x14001d902  push    rbx
0x14001d904  push    rbp
0x14001d905  sub     rsp, 28h
0x14001d909  mov     rbp, rdx
0x14001d90c  cmp     byte ptr [rbp+20h], 0
0x14001d910  jz      short loc_14001D935
0x14001d912  xor     r8d, r8d
0x14001d915  mov     rbx, [rbp+28h]
0x14001d919  mov     rdx, rbx
0x14001d91c  call    UdfUnpinCurrentBitmapPage
0x14001d921  lea     rcx, [rbx+228h]; Resource
0x14001d928  call    cs:__imp_ExReleaseResourceLite
0x14001d92f  nop     dword ptr [rax+rax+00h]
0x14001d934  nop
0x14001d935  cmp     byte ptr [rbp+21h], 0
0x14001d939  jz      short loc_14001D953
0x14001d93b  mov     rcx, [rbp+28h]
0x14001d93f  add     rcx, 5C8h; Resource
0x14001d946  call    cs:__imp_ExReleaseResourceLite
0x14001d94d  nop     dword ptr [rax+rax+00h]
0x14001d952  nop
0x14001d953  add     rsp, 28h
0x14001d957  pop     rbp
0x14001d958  pop     rbx
0x14001d959  retn
```

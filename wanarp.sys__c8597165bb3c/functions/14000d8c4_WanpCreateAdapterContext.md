# WanpCreateAdapterContext

- ea: `0x14000d8c4`
- end: `0x14000dc56`
- name: `WanpCreateAdapterContext`
- size: `914`
- prototype: `__int64 __fastcall(_OWORD *, const UNICODE_STRING *, __int64, PVOID *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000dc5c`

## callees

- `0x1400050b0`
- `0x1400051c0`
- `0x1400054c0`
- `0x14000d8c4`
- `0x1400112f0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000dc1c`
- `ntoskrnl!ExAllocatePool2` at `0x14000da0c`
- `ntoskrnl!ExAllocatePool2` at `0x14000da0c`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14000db4c`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14000db4c`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000dbcb`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000dbcb`

## pseudocode

```c
__int64 __fastcall WanpCreateAdapterContext(_OWORD *a1, const UNICODE_STRING *a2, __int64 a3, PVOID *a4)
{
  __int64 v7; // rax
  bool v8; // zf
  const UNICODE_STRING *v9; // rsi
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // ecx
  unsigned int v13; // r8d
  unsigned int Length; // eax
  unsigned int v15; // ecx
  unsigned int v16; // edx
  unsigned int v17; // ecx
  __int64 Pool2; // rax
  unsigned int v19; // ebx
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rbx
  _DWORD *v23; // rcx
  void *Src[2]; // [rsp+20h] [rbp-49h] BYREF
  __int64 v26; // [rsp+30h] [rbp-39h] BYREF
  int v27; // [rsp+38h] [rbp-31h]
  wchar_t v28; // [rsp+3Ch] [rbp-2Dh]
  __int16 v29; // [rsp+3Eh] [rbp-2Bh]
  _BYTE v30[80]; // [rsp+40h] [rbp-29h] BYREF

  *a4 = 0;
  *(_OWORD *)Src = 0;
  memset(v30, 0, sizeof(v30));
  v27 = *(_DWORD *)L"ICE";
  v28 = aDevice[6];
  v29 = 92;
  v26 = *(_QWORD *)L"\\DEVICE";
  ConvertGuidToString(a1, v30, 40);
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)&v26 + v7) );
  v8 = a2->Buffer == 0;
  v9 = (const UNICODE_STRING *)Src;
  v10 = (unsigned __int16)(2 * v7);
  Src[1] = &v26;
  if ( !v8 )
    v9 = a2;
  LOWORD(Src[0]) = v10;
  WORD1(Src[0]) = v10;
  if ( v10 + 2 < v10
    || v10 + 5 < v10 + 2
    || (v11 = (v10 + 5) & 0xFFFFFFFC, v12 = 2 * v11, 2 * v11 < v11)
    || (v13 = v12 + 392, v12 + 392 < v12)
    || (Length = v9->Length, Length + 2 < Length)
    || Length + 5 < Length + 2
    || (v15 = (Length + 5) & 0xFFFFFFFC, v16 = v13 + v15, v13 + v15 < v15)
    || (v17 = (Length >> 1) + v16, v17 < v16)
    || v17 + 2 < v17 )
  {
    v19 = -1073741675;
  }
  else
  {
    Pool2 = ExAllocatePool2(64, v17 + 2, 1634759255);
    *a4 = (PVOID)Pool2;
    if ( Pool2 )
    {
      *(_WORD *)(Pool2 + 56) = Src[0];
      v20 = (Pool2 + 395) & 0xFFFFFFFFFFFFFFFCuLL;
      *((_WORD *)*a4 + 29) = Src[0];
      *((_QWORD *)*a4 + 8) = v20;
      memmove(*((void **)*a4 + 8), Src[1], LOWORD(Src[0]));
      v21 = (LOWORD(Src[0]) + 5LL + v20) & 0xFFFFFFFFFFFFFFFCuLL;
      *((_WORD *)*a4 + 36) = Src[0];
      *((_WORD *)*a4 + 37) = Src[0];
      *((_QWORD *)*a4 + 10) = v21;
      memmove(*((void **)*a4 + 10), Src[1], LOWORD(Src[0]));
      *(_WORD *)(*((_QWORD *)*a4 + 10) + 2 * ((unsigned __int64)LOWORD(Src[0]) >> 1)) = 0;
      *((_BYTE *)*a4 + 149) = 1;
      v22 = (LOWORD(Src[0]) + 5LL + v21) & 0xFFFFFFFFFFFFFFFCuLL;
      *((_WORD *)*a4 + 44) = v9->Length;
      *((_WORD *)*a4 + 45) = v9->Length;
      *((_QWORD *)*a4 + 12) = v22;
      memmove(*((void **)*a4 + 12), v9->Buffer, v9->Length);
      *(_WORD *)(*((_QWORD *)*a4 + 12) + 2 * ((unsigned __int64)v9->Length >> 1)) = 0;
      *((_QWORD *)*a4 + 14) = (v22 + *((unsigned __int16 *)*a4 + 44) + 5LL) & 0xFFFFFFFFFFFFFFFCuLL;
      *((_WORD *)*a4 + 53) = (v9->Length >> 1) + 1;
      RtlUnicodeStringToAnsiString((PANSI_STRING)((char *)*a4 + 104), v9, 0);
      *(_OWORD *)((char *)*a4 + 152) = *a1;
      *((_DWORD *)*a4 + 36) = -1;
      *((_DWORD *)*a4 + 35) = -1;
      *((_BYTE *)*a4 + 148) = 0;
      v23 = *a4;
      v23[47] = 2017809152;
      *((_WORD *)v23 + 96) = 120;
      *((_BYTE *)*a4 + 191) = BYTE1(*((_DWORD *)*a4 + 34));
      *((_BYTE *)*a4 + 192) = *((_BYTE *)*a4 + 136);
      KeInitializeSpinLock((PKSPIN_LOCK)*a4 + 15);
      *((_DWORD *)*a4 + 12) = 1633968471;
      *((_DWORD *)*a4 + 90) = -1;
      *((_DWORD *)*a4 + 86) = 0;
      *((_DWORD *)*a4 + 32) = 1;
      _InterlockedAdd((volatile signed __int32 *)*a4 + 33, 1u);
      return 0;
    }
    v19 = -1073741670;
  }
  if ( *a4 )
  {
    ExFreePoolWithTag(*a4, 0);
    *a4 = 0;
  }
  return v19;
}

```

## disassembly

```asm
0x14000d8c4  mov     [rsp-8+arg_0], rbx
0x14000d8c9  mov     [rsp-8+arg_10], rsi
0x14000d8ce  push    rbp
0x14000d8cf  push    rdi
0x14000d8d0  push    r12
0x14000d8d2  push    r14
0x14000d8d4  push    r15
0x14000d8d6  lea     rbp, [rsp-37h]
0x14000d8db  sub     rsp, 0A0h
0x14000d8e2  mov     rax, cs:__security_cookie
0x14000d8e9  xor     rax, rsp
0x14000d8ec  mov     [rbp+57h+var_30], rax
0x14000d8f0  xor     r12d, r12d
0x14000d8f3  mov     rbx, rdx
0x14000d8f6  mov     r14, rcx
0x14000d8f9  mov     [r9], r12
0x14000d8fc  xorps   xmm0, xmm0
0x14000d8ff  lea     rcx, [rbp+57h+var_80]; void *
0x14000d903  xor     edx, edx; Val
0x14000d905  mov     rdi, r9
0x14000d908  lea     r8d, [r12+50h]; Size
0x14000d90d  movups  xmmword ptr [rbp+57h+Src], xmm0
0x14000d911  call    memset
0x14000d916  mov     eax, dword ptr cs:aDevice+8; "ICE"
0x14000d91c  lea     r8d, [r12+28h]
0x14000d921  movsd   xmm0, qword ptr cs:aDevice; "\\DEVICE"
0x14000d929  lea     rdx, [rbp+57h+var_80]
0x14000d92d  mov     [rbp+57h+var_88], eax
0x14000d930  mov     rcx, r14
0x14000d933  movzx   eax, word ptr cs:aDevice+0Ch; "E"
0x14000d93a  mov     [rbp+57h+var_84], ax
0x14000d93e  lea     eax, [r12+5Ch]
0x14000d943  mov     [rbp+57h+var_82], ax
0x14000d947  movsd   [rbp+57h+var_90], xmm0
0x14000d94c  call    ConvertGuidToString
0x14000d951  lea     rcx, [rbp+57h+var_90]
0x14000d955  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d959  inc     rax
0x14000d95c  cmp     [rcx+rax*2], r12w
0x14000d961  jnz     short loc_14000D959
0x14000d963  add     ax, ax
0x14000d966  lea     rcx, [rbp+57h+var_90]
0x14000d96a  cmp     [rbx+8], r12
0x14000d96e  lea     rsi, [rbp+57h+Src]
0x14000d972  movzx   eax, ax
0x14000d975  mov     [rbp+57h+Src+8], rcx
0x14000d979  cmovnz  rsi, rbx
0x14000d97d  mov     word ptr [rbp+57h+Src], ax
0x14000d981  mov     word ptr [rbp+57h+Src+2], ax
0x14000d985  lea     ecx, [rax+2]
0x14000d988  cmp     ecx, eax
0x14000d98a  jb      loc_14000DC0D
0x14000d990  lea     eax, [rcx+3]
0x14000d993  cmp     eax, ecx
0x14000d995  jb      loc_14000DC0D
0x14000d99b  mov     r9d, 0FFFFFFFCh
0x14000d9a1  and     eax, r9d
0x14000d9a4  lea     ecx, [rax+rax]
0x14000d9a7  cmp     ecx, eax
0x14000d9a9  jb      loc_14000DC0D
0x14000d9af  lea     r8d, [rcx+188h]
0x14000d9b6  cmp     r8d, ecx
0x14000d9b9  jb      loc_14000DC0D
0x14000d9bf  movzx   eax, word ptr [rsi]
0x14000d9c2  lea     edx, [rax+2]
0x14000d9c5  cmp     edx, eax
0x14000d9c7  jb      loc_14000DC0D
0x14000d9cd  lea     ecx, [rdx+3]
0x14000d9d0  cmp     ecx, edx
0x14000d9d2  jb      loc_14000DC0D
0x14000d9d8  and     ecx, r9d
0x14000d9db  lea     edx, [r8+rcx]
0x14000d9df  cmp     edx, ecx
0x14000d9e1  jb      loc_14000DC0D
0x14000d9e7  shr     eax, 1
0x14000d9e9  lea     ecx, [rax+rdx]
0x14000d9ec  cmp     ecx, edx
0x14000d9ee  jb      loc_14000DC0D
0x14000d9f4  lea     eax, [rcx+2]
0x14000d9f7  cmp     eax, ecx
0x14000d9f9  jb      loc_14000DC0D
0x14000d9ff  mov     edx, eax
0x14000da01  mov     ecx, 40h ; '@'
0x14000da06  mov     r8d, 61707257h
0x14000da0c  call    cs:__imp_ExAllocatePool2
0x14000da13  nop     dword ptr [rax+rax+00h]
0x14000da18  mov     [rdi], rax
0x14000da1b  mov     rcx, rax
0x14000da1e  test    rax, rax
0x14000da21  jnz     short loc_14000DA2D
0x14000da23  mov     ebx, 0C000009Ah
0x14000da28  jmp     loc_14000DC12
0x14000da2d  lea     rbx, [rax+18Bh]
0x14000da34  movzx   eax, word ptr [rbp+57h+Src]
0x14000da38  mov     [rcx+38h], ax
0x14000da3c  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000da40  mov     rcx, [rdi]
0x14000da43  movzx   eax, word ptr [rbp+57h+Src]
0x14000da47  mov     [rcx+3Ah], ax
0x14000da4b  mov     rax, [rdi]
0x14000da4e  mov     [rax+40h], rbx
0x14000da52  mov     rcx, [rdi]
0x14000da55  movzx   r8d, word ptr [rbp+57h+Src]; Size
0x14000da5a  mov     rdx, [rbp+57h+Src+8]; Src
0x14000da5e  mov     rcx, [rcx+40h]; void *
0x14000da62  call    memmove
0x14000da67  movzx   ecx, word ptr [rbp+57h+Src]
0x14000da6b  lea     rax, [rcx+5]
0x14000da6f  add     rbx, rax
0x14000da72  mov     rax, [rdi]
0x14000da75  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000da79  mov     [rax+48h], cx
0x14000da7d  mov     rcx, [rdi]
0x14000da80  movzx   eax, word ptr [rbp+57h+Src]
0x14000da84  mov     [rcx+4Ah], ax
0x14000da88  mov     rax, [rdi]
0x14000da8b  mov     [rax+50h], rbx
0x14000da8f  mov     rcx, [rdi]
0x14000da92  movzx   r8d, word ptr [rbp+57h+Src]; Size
0x14000da97  mov     rdx, [rbp+57h+Src+8]; Src
0x14000da9b  mov     rcx, [rcx+50h]; void *
0x14000da9f  call    memmove
0x14000daa4  mov     rax, [rdi]
0x14000daa7  mov     r15d, 1
0x14000daad  movzx   edx, word ptr [rbp+57h+Src]
0x14000dab1  shr     rdx, 1
0x14000dab4  mov     rcx, [rax+50h]
0x14000dab8  mov     [rcx+rdx*2], r12w
0x14000dabd  mov     rax, [rdi]
0x14000dac0  mov     [rax+95h], r15b
0x14000dac7  movzx   eax, word ptr [rbp+57h+Src]
0x14000dacb  mov     rcx, [rdi]
0x14000dace  add     rax, 5
0x14000dad2  add     rbx, rax
0x14000dad5  movzx   eax, word ptr [rsi]
0x14000dad8  and     rbx, 0FFFFFFFFFFFFFFFCh
0x14000dadc  mov     [rcx+58h], ax
0x14000dae0  mov     rcx, [rdi]
0x14000dae3  movzx   eax, word ptr [rsi]
0x14000dae6  mov     [rcx+5Ah], ax
0x14000daea  mov     rax, [rdi]
0x14000daed  mov     [rax+60h], rbx
0x14000daf1  mov     rcx, [rdi]
0x14000daf4  movzx   r8d, word ptr [rsi]; Size
0x14000daf8  mov     rdx, [rsi+8]; Src
0x14000dafc  mov     rcx, [rcx+60h]; void *
0x14000db00  call    memmove
0x14000db05  mov     rax, [rdi]
0x14000db08  movzx   edx, word ptr [rsi]
0x14000db0b  shr     rdx, 1
0x14000db0e  mov     rcx, [rax+60h]
0x14000db12  mov     [rcx+rdx*2], r12w
0x14000db17  mov     rdx, rsi; SourceString
0x14000db1a  mov     r8, [rdi]
0x14000db1d  movzx   ecx, word ptr [r8+58h]
0x14000db22  add     rcx, 5
0x14000db26  add     rcx, rbx
0x14000db29  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14000db2d  mov     [r8+70h], rcx
0x14000db31  xor     r8d, r8d; AllocateDestinationString
0x14000db34  movzx   ecx, word ptr [rsi]
0x14000db37  mov     rax, [rdi]
0x14000db3a  shr     cx, 1
0x14000db3d  add     cx, r15w
0x14000db41  mov     [rax+6Ah], cx
0x14000db45  mov     rcx, [rdi]
0x14000db48  add     rcx, 68h ; 'h'; DestinationString
0x14000db4c  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14000db53  nop     dword ptr [rax+rax+00h]
0x14000db58  mov     rax, [rdi]
0x14000db5b  or      ebx, 0FFFFFFFFh
0x14000db5e  movups  xmm0, xmmword ptr [r14]
0x14000db62  movdqu  xmmword ptr [rax+98h], xmm0
0x14000db6a  mov     rax, [rdi]
0x14000db6d  mov     [rax+90h], ebx
0x14000db73  mov     rax, [rdi]
0x14000db76  mov     [rax+8Ch], ebx
0x14000db7c  mov     rax, [rdi]
0x14000db7f  mov     [rax+94h], r12b
0x14000db86  mov     eax, cs:dword_140007290
0x14000db8c  mov     rcx, [rdi]
0x14000db8f  mov     [rcx+0BCh], eax
0x14000db95  movzx   eax, cs:word_140007294
0x14000db9c  mov     [rcx+0C0h], ax
0x14000dba3  mov     rcx, [rdi]
0x14000dba6  mov     eax, [rcx+88h]
0x14000dbac  shr     eax, 8
0x14000dbaf  mov     [rcx+0BFh], al
0x14000dbb5  mov     rcx, [rdi]
0x14000dbb8  mov     al, [rcx+88h]
0x14000dbbe  mov     [rcx+0C0h], al
0x14000dbc4  mov     rcx, [rdi]
0x14000dbc7  add     rcx, 78h ; 'x'; SpinLock
0x14000dbcb  call    cs:__imp_KeInitializeSpinLock
0x14000dbd2  nop     dword ptr [rax+rax+00h]
0x14000dbd7  mov     rax, [rdi]
0x14000dbda  mov     dword ptr [rax+30h], 61646157h
0x14000dbe1  mov     rax, [rdi]
0x14000dbe4  mov     [rax+168h], ebx
0x14000dbea  mov     rax, [rdi]
0x14000dbed  mov     [rax+158h], r12d
0x14000dbf4  mov     rax, [rdi]
0x14000dbf7  mov     [rax+80h], r15d
0x14000dbfe  mov     rax, [rdi]
0x14000dc01  lock add [rax+84h], r15d
0x14000dc09  xor     eax, eax
0x14000dc0b  jmp     short loc_14000DC2D
0x14000dc0d  mov     ebx, 0C0000095h
0x14000dc12  mov     rcx, [rdi]; P
0x14000dc15  test    rcx, rcx
0x14000dc18  jz      short loc_14000DC2B
0x14000dc1a  xor     edx, edx; Tag
0x14000dc1c  call    cs:__imp_ExFreePoolWithTag
0x14000dc23  nop     dword ptr [rax+rax+00h]
0x14000dc28  mov     [rdi], r12
0x14000dc2b  mov     eax, ebx
0x14000dc2d  mov     rcx, [rbp+57h+var_30]
0x14000dc31  xor     rcx, rsp; StackCookie
0x14000dc34  call    __security_check_cookie
0x14000dc39  lea     r11, [rsp+0C0h+var_20]
0x14000dc41  mov     rbx, [r11+30h]
0x14000dc45  mov     rsi, [r11+40h]
0x14000dc49  mov     rsp, r11
0x14000dc4c  pop     r15
0x14000dc4e  pop     r14
0x14000dc50  pop     r12
0x14000dc52  pop     rdi
0x14000dc53  pop     rbp
0x14000dc54  retn
```

# SetDot1xConnectionProfile

- ea: `0x18003f220`
- end: `0x18003f3b8`
- name: `SetDot1xConnectionProfile`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18003e410`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x18003f220`
- `0x18004371c`
- `0x180043c60`
- `0x18006013c`

## import_xrefs

- `OneX!OneXCreateDefaultProfile` at `0x18003f2e7`
- `OneX!OneXCreateDefaultProfile` at `0x18003f2e7`
- `OneX!OneXFreeMemory` at `0x18003f376`
- `OneX!OneXFreeMemory` at `0x18003f376`

## pseudocode

```c
__int64 __fastcall SetDot1xConnectionProfile(__int64 a1, __int64 a2)
{
  union DOT11_OUI_HEADER *v3; // rcx
  unsigned int v4; // ebx
  unsigned int v5; // edi
  unsigned int MSMSecMemory; // eax
  union DOT11_OUI_HEADER *v7; // rcx
  __int64 v8; // rdx
  void *v10[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int Size; // [rsp+70h] [rbp+30h] BYREF
  int Size_4; // [rsp+74h] [rbp+34h]
  void *Src; // [rsp+78h] [rbp+38h] BYREF

  Size_4 = HIDWORD(a1);
  Size = 0;
  *(_OWORD *)v10 = 0;
  Src = 0;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, WPP_adc6fb6c3a183d1c32ad8d6dd62baabe_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( !*(_DWORD *)(a2 + 32) )
  {
    v4 = 0;
    if ( v3 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)v3 + 2), 165, WPP_adc6fb6c3a183d1c32ad8d6dd62baabe_Traceguids);
    v5 = (unsigned int)v10[0];
    goto LABEL_23;
  }
  if ( v3 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)v3 + 2), 166, WPP_adc6fb6c3a183d1c32ad8d6dd62baabe_Traceguids);
  MSMSecMemory = OneXCreateDefaultProfile(1, 0, &Size, &Src, 0);
  v4 = MSMSecMemory;
  if ( MSMSecMemory )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v8 = 168;
LABEL_20:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_adc6fb6c3a183d1c32ad8d6dd62baabe_Traceguids, MSMSecMemory);
LABEL_21:
    FreeRawData(v10);
    goto LABEL_24;
  }
  MSMSecMemory = AllocateMSMSecMemory(Size, &v10[1]);
  v4 = MSMSecMemory;
  if ( MSMSecMemory )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_21;
    }
    v8 = 169;
    goto LABEL_20;
  }
  v5 = Size;
  memcpy_0(v10[1], Src, Size);
LABEL_23:
  *(void **)(a2 + 48) = v10[1];
  *(_DWORD *)(a2 + 40) = v5;
LABEL_24:
  if ( Src )
    OneXFreeMemory(Src);
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, WPP_adc6fb6c3a183d1c32ad8d6dd62baabe_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18003f220  mov     [rsp-28h+arg_10], rbx
0x18003f225  mov     [rsp-28h+Size], rcx
0x18003f22a  push    rbp
0x18003f22b  push    rsi
0x18003f22c  push    rdi
0x18003f22d  push    r12
0x18003f22f  push    r15
0x18003f231  mov     rbp, rsp
0x18003f234  sub     rsp, 40h
0x18003f238  xorps   xmm0, xmm0
0x18003f23b  mov     dword ptr [rbp+Size], 0
0x18003f242  movups  xmmword ptr [rbp+var_10], xmm0
0x18003f246  mov     rsi, rdx
0x18003f249  mov     [rbp+Src], 0
0x18003f251  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f258  lea     r15, WPP_GLOBAL_Control
0x18003f25f  lea     r12, WPP_adc6fb6c3a183d1c32ad8d6dd62baabe_Traceguids
0x18003f266  cmp     rcx, r15
0x18003f269  jz      short loc_18003F289
0x18003f26b  test    byte ptr [rcx+1Ch], 8
0x18003f26f  jz      short loc_18003F289
0x18003f271  mov     rcx, [rcx+10h]
0x18003f275  mov     edx, 0A4h
0x18003f27a  mov     r8, r12
0x18003f27d  call    WPP_SF_
0x18003f282  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f289  cmp     dword ptr [rsi+20h], 0
0x18003f28d  jnz     short loc_18003F2B5
0x18003f28f  xor     ebx, ebx
0x18003f291  cmp     rcx, r15
0x18003f294  jz      short loc_18003F2AD
0x18003f296  test    byte ptr [rcx+1Ch], 2
0x18003f29a  jz      short loc_18003F2AD
0x18003f29c  mov     rcx, [rcx+10h]
0x18003f2a0  mov     edx, 0A5h
0x18003f2a5  mov     r8, r12
0x18003f2a8  call    WPP_SF_
0x18003f2ad  mov     edi, dword ptr [rbp+var_10]
0x18003f2b0  jmp     loc_18003F362
0x18003f2b5  cmp     rcx, r15
0x18003f2b8  jz      short loc_18003F2D1
0x18003f2ba  test    byte ptr [rcx+1Ch], 2
0x18003f2be  jz      short loc_18003F2D1
0x18003f2c0  mov     rcx, [rcx+10h]
0x18003f2c4  mov     edx, 0A6h
0x18003f2c9  mov     r8, r12
0x18003f2cc  call    WPP_SF_
0x18003f2d1  xor     edx, edx
0x18003f2d3  mov     [rsp+40h+var_20], 0
0x18003f2dc  lea     r9, [rbp+Src]
0x18003f2e0  lea     r8, [rbp+Size]
0x18003f2e4  lea     ecx, [rdx+1]
0x18003f2e7  call    cs:__imp_OneXCreateDefaultProfile
0x18003f2ed  mov     ebx, eax
0x18003f2ef  test    eax, eax
0x18003f2f1  jz      short loc_18003F30C
0x18003f2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f2fa  cmp     rcx, r15
0x18003f2fd  jz      short loc_18003F344
0x18003f2ff  test    byte ptr [rcx+1Ch], 1
0x18003f303  jz      short loc_18003F344
0x18003f305  mov     edx, 0A8h
0x18003f30a  jmp     short loc_18003F335
0x18003f30c  mov     ecx, dword ptr [rbp+Size]
0x18003f30f  lea     rdx, [rbp+var_10+8]
0x18003f313  call    AllocateMSMSecMemory
0x18003f318  mov     ebx, eax
0x18003f31a  test    eax, eax
0x18003f31c  jz      short loc_18003F34F
0x18003f31e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f325  cmp     rcx, r15
0x18003f328  jz      short loc_18003F344
0x18003f32a  test    byte ptr [rcx+1Ch], 1
0x18003f32e  jz      short loc_18003F344
0x18003f330  mov     edx, 0A9h
0x18003f335  mov     rcx, [rcx+10h]
0x18003f339  mov     r9d, eax
0x18003f33c  mov     r8, r12
0x18003f33f  call    WPP_SF_d
0x18003f344  lea     rcx, [rbp+var_10]
0x18003f348  call    FreeRawData
0x18003f34d  jmp     short loc_18003F36D
0x18003f34f  mov     edi, dword ptr [rbp+Size]
0x18003f352  mov     rdx, [rbp+Src]; Src
0x18003f356  mov     r8d, edi; Size
0x18003f359  mov     rcx, [rbp+var_10+8]; void *
0x18003f35d  call    memcpy_0
0x18003f362  mov     rax, [rbp+var_10+8]
0x18003f366  mov     [rsi+30h], rax
0x18003f36a  mov     [rsi+28h], edi
0x18003f36d  mov     rcx, [rbp+Src]
0x18003f371  test    rcx, rcx
0x18003f374  jz      short loc_18003F37C
0x18003f376  call    cs:__imp_OneXFreeMemory
0x18003f37c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f383  cmp     rcx, r15
0x18003f386  jz      short loc_18003F3A2
0x18003f388  test    byte ptr [rcx+1Ch], 8
0x18003f38c  jz      short loc_18003F3A2
0x18003f38e  mov     rcx, [rcx+10h]
0x18003f392  mov     edx, 0AAh
0x18003f397  mov     r9d, ebx
0x18003f39a  mov     r8, r12
0x18003f39d  call    WPP_SF_d
0x18003f3a2  mov     eax, ebx
0x18003f3a4  mov     rbx, [rsp+40h+arg_10]
0x18003f3ac  add     rsp, 40h
0x18003f3b0  pop     r15
0x18003f3b2  pop     r12
0x18003f3b4  pop     rdi
0x18003f3b5  pop     rsi
0x18003f3b6  pop     rbp
0x18003f3b7  retn
```

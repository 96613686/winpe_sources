# SetDot1xConnectionProfile

- ea: `0x180020d94`
- end: `0x180020f92`
- name: `SetDot1xConnectionProfile`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180020c50`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18000c730`
- `0x18000d5e4`
- `0x18001d370`
- `0x18001f29c`
- `0x180020d94`
- `0x180044554`

## import_xrefs

- `OneX!OneXFreeMemory` at `0x180020f49`
- `OneX!OneXFreeMemory` at `0x180020f49`
- `OneX!OneXCreateDefaultProfile` at `0x180020eb9`
- `OneX!OneXCreateDefaultProfile` at `0x180020eb9`

## pseudocode

```c
__int64 __fastcall SetDot1xConnectionProfile(__int64 a1, __int64 a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  unsigned int MSMSecMemory; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  void *v11[2]; // [rsp+30h] [rbp-10h] BYREF
  size_t Size; // [rsp+68h] [rbp+28h] BYREF
  void *Src; // [rsp+70h] [rbp+30h] BYREF

  LODWORD(Size) = 0;
  *(_OWORD *)v11 = 0;
  Src = 0;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, WPP_adc6fb6c3a183d1c32ad8d6dd62baabe_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*(_DWORD *)(a2 + 32) )
  {
    v5 = 0;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
      WPP_SF_(v4[2], 165, WPP_adc6fb6c3a183d1c32ad8d6dd62baabe_Traceguids);
LABEL_27:
    *(void **)(a2 + 48) = v11[1];
    *(_DWORD *)(a2 + 40) = v11[0];
    if ( !v5 )
      goto LABEL_29;
    goto LABEL_28;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
    WPP_SF_(v4[2], 166, WPP_adc6fb6c3a183d1c32ad8d6dd62baabe_Traceguids);
  if ( a1 && (unsigned int)RawDataIsNonEmpty(a1 + 40) )
  {
    MSMSecMemory = CopyRawData(v6, v11);
    v5 = MSMSecMemory;
    if ( !MSMSecMemory )
      goto LABEL_27;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 167;
LABEL_17:
      WPP_SF_d(v8[2], v9, WPP_adc6fb6c3a183d1c32ad8d6dd62baabe_Traceguids, MSMSecMemory);
    }
  }
  else
  {
    MSMSecMemory = OneXCreateDefaultProfile(1, 0, &Size, &Src, 0);
    v5 = MSMSecMemory;
    if ( MSMSecMemory )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v9 = 168;
      goto LABEL_17;
    }
    MSMSecMemory = AllocateMSMSecMemory((unsigned int)Size);
    v5 = MSMSecMemory;
    if ( !MSMSecMemory )
    {
      LODWORD(v11[0]) = Size;
      memcpy_0(v11[1], Src, (unsigned int)Size);
      goto LABEL_27;
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = 169;
      goto LABEL_17;
    }
  }
LABEL_28:
  FreeRawData(v11);
LABEL_29:
  if ( Src )
    OneXFreeMemory();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 170, WPP_adc6fb6c3a183d1c32ad8d6dd62baabe_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180020d94  mov     [rsp-18h+arg_0], rbx
0x180020d99  mov     [rsp-18h+arg_18], rdi
0x180020d9e  push    rbp
0x180020d9f  push    r14
0x180020da1  push    r15
0x180020da3  mov     rbp, rsp
0x180020da6  sub     rsp, 40h
0x180020daa  xorps   xmm0, xmm0
0x180020dad  mov     dword ptr [rbp+Size], 0
0x180020db4  movups  xmmword ptr [rbp+var_10], xmm0
0x180020db8  mov     rdi, rdx
0x180020dbb  mov     [rbp+Src], 0
0x180020dc3  mov     rbx, rcx
0x180020dc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dcd  lea     r14, WPP_GLOBAL_Control
0x180020dd4  lea     r15, WPP_adc6fb6c3a183d1c32ad8d6dd62baabe_Traceguids
0x180020ddb  cmp     rcx, r14
0x180020dde  jz      short loc_180020DFE
0x180020de0  test    byte ptr [rcx+1Ch], 8
0x180020de4  jz      short loc_180020DFE
0x180020de6  mov     rcx, [rcx+10h]
0x180020dea  mov     edx, 0A4h
0x180020def  mov     r8, r15
0x180020df2  call    WPP_SF_
0x180020df7  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dfe  cmp     dword ptr [rdi+20h], 0
0x180020e02  jnz     short loc_180020E2F
0x180020e04  xor     ebx, ebx
0x180020e06  cmp     rcx, r14
0x180020e09  jz      loc_180020F25
0x180020e0f  test    byte ptr [rcx+1Ch], 2
0x180020e13  jz      loc_180020F25
0x180020e19  mov     rcx, [rcx+10h]
0x180020e1d  mov     edx, 0A5h
0x180020e22  mov     r8, r15
0x180020e25  call    WPP_SF_
0x180020e2a  jmp     loc_180020F25
0x180020e2f  cmp     rcx, r14
0x180020e32  jz      short loc_180020E4B
0x180020e34  test    byte ptr [rcx+1Ch], 2
0x180020e38  jz      short loc_180020E4B
0x180020e3a  mov     rcx, [rcx+10h]
0x180020e3e  mov     edx, 0A6h
0x180020e43  mov     r8, r15
0x180020e46  call    WPP_SF_
0x180020e4b  test    rbx, rbx
0x180020e4e  jz      short loc_180020EA3
0x180020e50  lea     rcx, [rbx+28h]
0x180020e54  call    RawDataIsNonEmpty
0x180020e59  test    eax, eax
0x180020e5b  jz      short loc_180020EA3
0x180020e5d  lea     rdx, [rbp+var_10]
0x180020e61  call    CopyRawData
0x180020e66  mov     ebx, eax
0x180020e68  test    eax, eax
0x180020e6a  jz      loc_180020F25
0x180020e70  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e77  cmp     rcx, r14
0x180020e7a  jz      loc_180020F37
0x180020e80  test    byte ptr [rcx+1Ch], 1
0x180020e84  jz      loc_180020F37
0x180020e8a  mov     edx, 0A7h
0x180020e8f  mov     rcx, [rcx+10h]
0x180020e93  mov     r9d, eax
0x180020e96  mov     r8, r15
0x180020e99  call    WPP_SF_d
0x180020e9e  jmp     loc_180020F37
0x180020ea3  xor     edx, edx
0x180020ea5  mov     [rsp+40h+var_20], 0
0x180020eae  lea     r9, [rbp+Src]
0x180020eb2  lea     r8, [rbp+Size]
0x180020eb6  lea     ecx, [rdx+1]
0x180020eb9  call    cs:__imp_OneXCreateDefaultProfile
0x180020ec0  nop     dword ptr [rax+rax+00h]
0x180020ec5  mov     ebx, eax
0x180020ec7  test    eax, eax
0x180020ec9  jz      short loc_180020EE4
0x180020ecb  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ed2  cmp     rcx, r14
0x180020ed5  jz      short loc_180020F37
0x180020ed7  test    byte ptr [rcx+1Ch], 1
0x180020edb  jz      short loc_180020F37
0x180020edd  mov     edx, 0A8h
0x180020ee2  jmp     short loc_180020E8F
0x180020ee4  mov     ecx, dword ptr [rbp+Size]; dwBytes
0x180020ee7  lea     rdx, [rbp+var_10+8]
0x180020eeb  call    AllocateMSMSecMemory
0x180020ef0  mov     ebx, eax
0x180020ef2  test    eax, eax
0x180020ef4  jz      short loc_180020F0F
0x180020ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180020efd  cmp     rcx, r14
0x180020f00  jz      short loc_180020F37
0x180020f02  test    byte ptr [rcx+1Ch], 1
0x180020f06  jz      short loc_180020F37
0x180020f08  mov     edx, 0A9h
0x180020f0d  jmp     short loc_180020E8F
0x180020f0f  mov     eax, dword ptr [rbp+Size]
0x180020f12  mov     rdx, [rbp+Src]; Src
0x180020f16  mov     r8d, eax; Size
0x180020f19  mov     rcx, [rbp+var_10+8]; void *
0x180020f1d  mov     dword ptr [rbp+var_10], eax
0x180020f20  call    memcpy_0
0x180020f25  mov     rax, [rbp+var_10+8]
0x180020f29  mov     [rdi+30h], rax
0x180020f2d  mov     eax, dword ptr [rbp+var_10]
0x180020f30  mov     [rdi+28h], eax
0x180020f33  test    ebx, ebx
0x180020f35  jz      short loc_180020F40
0x180020f37  lea     rcx, [rbp+var_10]
0x180020f3b  call    FreeRawData
0x180020f40  mov     rcx, [rbp+Src]
0x180020f44  test    rcx, rcx
0x180020f47  jz      short loc_180020F55
0x180020f49  call    cs:__imp_OneXFreeMemory
0x180020f50  nop     dword ptr [rax+rax+00h]
0x180020f55  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f5c  cmp     rcx, r14
0x180020f5f  jz      short loc_180020F7B
0x180020f61  test    byte ptr [rcx+1Ch], 8
0x180020f65  jz      short loc_180020F7B
0x180020f67  mov     rcx, [rcx+10h]
0x180020f6b  mov     edx, 0AAh
0x180020f70  mov     r9d, ebx
0x180020f73  mov     r8, r15
0x180020f76  call    WPP_SF_d
0x180020f7b  mov     rdi, [rsp+40h+arg_18]
0x180020f80  mov     eax, ebx
0x180020f82  mov     rbx, [rsp+40h+arg_0]
0x180020f87  add     rsp, 40h
0x180020f8b  pop     r15
0x180020f8d  pop     r14
0x180020f8f  pop     rbp
0x180020f90  retn
```

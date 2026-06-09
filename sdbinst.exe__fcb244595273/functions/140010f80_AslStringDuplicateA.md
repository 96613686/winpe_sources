# AslStringDuplicateA

- ea: `0x140010f80`
- end: `0x140011124`
- name: `AslStringDuplicateA`
- size: `420`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000d710`

## callees

- `0x14001008c`
- `0x140010f80`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140011011`
- `ntdll!RtlAllocateHeap` at `0x140011011`
- `ntdll!RtlFreeHeap` at `0x1400110e7`
- `ntdll!RtlFreeHeap` at `0x1400110e7`

## string_xrefs

- `0x1400110b3`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslStringDuplicateA(_QWORD *a1)
{
  const unsigned __int16 *v2; // r14
  __int64 v3; // r8
  const unsigned __int16 *v4; // rax
  unsigned int v5; // ebx
  unsigned __int64 v6; // r9
  const char *v7; // r9
  __int64 v8; // r8
  unsigned __int64 v9; // rdi
  _BYTE *Heap; // rax
  _BYTE *v11; // rsi
  __int64 v12; // rax
  _BYTE *v13; // rcx
  _BYTE *v14; // rax

  *a1 = 0;
  v2 = &dword_1400326D4;
  v3 = 0x7FFFFFFF;
  v4 = &dword_1400326D4;
  do
  {
    if ( !*(_BYTE *)v4 )
      break;
    v4 = (const unsigned __int16 *)((char *)v4 + 1);
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0xC000000D : 0;
  v6 = (0x7FFFFFFF - v3) & -(__int64)(v3 != 0);
  if ( !v3 )
  {
    v7 = "RtlStringCchLengthA failed [%x]";
    v8 = 479;
LABEL_23:
    AslLogCallPrintf(1, "AslStringDuplicateA", v8, v7, v5);
    return v5;
  }
  v9 = v6 + 1;
  if ( v6 + 1 < v6 )
  {
    v5 = -1073741675;
    v7 = "SIZE_T arithmetic failed [%x]";
    v8 = 490;
    goto LABEL_23;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v6 + 1);
  v11 = Heap;
  if ( Heap )
  {
    if ( v9 )
    {
      if ( v9 <= 0x7FFFFFFF )
      {
        v12 = 2147483646;
        v13 = v11;
        do
        {
          if ( !v12 )
            break;
          if ( !*(_BYTE *)v2 )
            break;
          *v13 = *(_BYTE *)v2;
          v2 = (const unsigned __int16 *)((char *)v2 + 1);
          ++v13;
          --v12;
          --v9;
        }
        while ( v9 );
        v14 = v13 - 1;
        v5 = v9 == 0 ? 0x80000005 : 0;
        if ( v9 )
          v14 = v13;
        *v14 = 0;
        if ( v9 )
        {
          *a1 = v11;
          return 0;
        }
      }
      else
      {
        v5 = -1073741811;
        *Heap = 0;
      }
    }
    else
    {
      v5 = -1073741811;
    }
    AslLogCallPrintf(1, "AslStringDuplicateA", 507, "RtlStringCchCopyW failed [%x]", v5);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    return v5;
  }
  v5 = -1073741801;
  AslLogCallPrintf(1, "AslStringDuplicateA", 497, "Out of memory");
  return v5;
}

```

## disassembly

```asm
0x140010f80  push    rbx
0x140010f82  push    rsi
0x140010f83  push    rdi
0x140010f84  push    r14
0x140010f86  push    r15
0x140010f88  sub     rsp, 30h
0x140010f8c  mov     r15, rcx
0x140010f8f  mov     qword ptr [rcx], 0
0x140010f96  mov     ecx, 7FFFFFFFh
0x140010f9b  lea     r14, dword_1400326D4
0x140010fa2  mov     r8d, ecx
0x140010fa5  mov     rax, r14
0x140010fa8  cmp     byte ptr [rax], 0
0x140010fab  jz      short loc_140010FB6
0x140010fad  inc     rax
0x140010fb0  sub     r8, 1
0x140010fb4  jnz     short loc_140010FA8
0x140010fb6  mov     rax, r8
0x140010fb9  mov     rdx, rcx
0x140010fbc  neg     rax
0x140010fbf  mov     rax, r8
0x140010fc2  sbb     ebx, ebx
0x140010fc4  sub     rdx, r8
0x140010fc7  not     ebx
0x140010fc9  and     ebx, 0C000000Dh
0x140010fcf  neg     rax
0x140010fd2  sbb     r9, r9
0x140010fd5  and     r9, rdx
0x140010fd8  test    r8, r8
0x140010fdb  jnz     short loc_140010FEF
0x140010fdd  lea     r9, aRtlstringcchle_0; "RtlStringCchLengthA failed [%x]"
0x140010fe4  mov     r8d, 1DFh
0x140010fea  jmp     loc_140011101
0x140010fef  lea     rdi, [r9+1]
0x140010ff3  cmp     rdi, r9
0x140010ff6  jb      loc_1400110EF
0x140010ffc  mov     rcx, gs:60h
0x140011005  mov     r8, rdi; Size
0x140011008  mov     edx, 8; Flags
0x14001100d  mov     rcx, [rcx+30h]; HeapHandle
0x140011011  call    cs:__imp_RtlAllocateHeap
0x140011017  mov     rsi, rax
0x14001101a  test    rax, rax
0x14001101d  jnz     short loc_140011045
0x14001101f  lea     r9, aOutOfMemory; "Out of memory"
0x140011026  mov     r8d, 1F1h
0x14001102c  lea     rdx, aAslstringdupli_2; "AslStringDuplicateA"
0x140011033  mov     ebx, 0C0000017h
0x140011038  lea     ecx, [rax+1]
0x14001103b  call    AslLogCallPrintf
0x140011040  jmp     loc_140011116
0x140011045  test    rdi, rdi
0x140011048  jz      short loc_1400110A6
0x14001104a  cmp     rdi, 7FFFFFFFh
0x140011051  jbe     short loc_14001105A
0x140011053  mov     ebx, 0C000000Dh
0x140011058  jmp     short loc_1400110B0
0x14001105a  mov     eax, 7FFFFFFEh
0x14001105f  mov     rcx, rsi
0x140011062  test    rax, rax
0x140011065  jz      short loc_14001107F
0x140011067  mov     dl, [r14]
0x14001106a  test    dl, dl
0x14001106c  jz      short loc_14001107F
0x14001106e  mov     [rcx], dl
0x140011070  inc     r14
0x140011073  inc     rcx
0x140011076  dec     rax
0x140011079  sub     rdi, 1
0x14001107d  jnz     short loc_140011062
0x14001107f  mov     rax, rdi
0x140011082  neg     rax
0x140011085  lea     rax, [rcx-1]
0x140011089  sbb     ebx, ebx
0x14001108b  not     ebx
0x14001108d  and     ebx, 80000005h
0x140011093  test    rdi, rdi
0x140011096  cmovnz  rax, rcx
0x14001109a  mov     byte ptr [rax], 0
0x14001109d  jz      short loc_1400110B3
0x14001109f  mov     [r15], rsi
0x1400110a2  xor     ebx, ebx
0x1400110a4  jmp     short loc_140011116
0x1400110a6  mov     ebx, 0C000000Dh
0x1400110ab  test    rdi, rdi
0x1400110ae  jz      short loc_1400110B3
0x1400110b0  mov     byte ptr [rax], 0
0x1400110b3  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x1400110ba  mov     [rsp+58h+var_38], ebx
0x1400110be  mov     r8d, 1FBh
0x1400110c4  lea     rdx, aAslstringdupli_2; "AslStringDuplicateA"
0x1400110cb  mov     ecx, 1
0x1400110d0  call    AslLogCallPrintf
0x1400110d5  mov     rcx, gs:60h
0x1400110de  mov     r8, rsi; P
0x1400110e1  xor     edx, edx; Flags
0x1400110e3  mov     rcx, [rcx+30h]; HeapHandle
0x1400110e7  call    cs:__imp_RtlFreeHeap
0x1400110ed  jmp     short loc_140011116
0x1400110ef  mov     ebx, 0C0000095h
0x1400110f4  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x1400110fb  mov     r8d, 1EAh
0x140011101  lea     rdx, aAslstringdupli_2; "AslStringDuplicateA"
0x140011108  mov     [rsp+58h+var_38], ebx
0x14001110c  mov     ecx, 1
0x140011111  call    AslLogCallPrintf
0x140011116  mov     eax, ebx
0x140011118  add     rsp, 30h
0x14001111c  pop     r15
0x14001111e  pop     r14
0x140011120  pop     rdi
0x140011121  pop     rsi
0x140011122  pop     rbx
0x140011123  retn
```

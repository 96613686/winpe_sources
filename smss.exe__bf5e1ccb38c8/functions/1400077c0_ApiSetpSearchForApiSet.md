# ApiSetpSearchForApiSet

- ea: `0x1400077c0`
- end: `0x1400078b0`
- name: `ApiSetpSearchForApiSet`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400080c0`

## callees

- `0x1400077c0`

## import_xrefs

- `ntdll!RtlCompareUnicodeStrings` at `0x14000788c`
- `ntdll!RtlCompareUnicodeStrings` at `0x14000788c`

## pseudocode

```c
__int64 __fastcall ApiSetpSearchForApiSet(_DWORD *a1, const WCHAR *a2, unsigned __int16 a3)
{
  SIZE_T v3; // rbp
  unsigned int v4; // r10d
  const WCHAR *v6; // r9
  unsigned int i; // r11d
  WCHAR v8; // ax
  __int64 v9; // rbx
  int v10; // r11d
  int v11; // r9d
  int v12; // r8d
  char *v13; // rcx
  bool v14; // cf
  bool v15; // cc
  char *v16; // rcx

  v3 = a3;
  v4 = 0;
  if ( a3 )
  {
    v6 = a2;
    for ( i = 0; i < a3; ++i )
    {
      v8 = *v6;
      if ( (unsigned __int16)(*v6 - 65) <= 0x19u )
        v8 += 32;
      ++v6;
      v4 = v4 * a1[6] + v8;
    }
  }
  v9 = 0;
  v10 = 0;
  v11 = a1[3] - 1;
  while ( v10 <= v11 )
  {
    v12 = (v10 + v11) >> 1;
    v13 = (char *)a1 + (unsigned int)a1[5];
    v14 = v4 < *(_DWORD *)&v13[8 * v12];
    v15 = v4 <= *(_DWORD *)&v13[8 * v12];
    v16 = &v13[8 * v12];
    if ( v14 )
    {
      v11 = v12 - 1;
    }
    else
    {
      if ( v15 )
      {
        v9 = (__int64)&a1[6 * *((unsigned int *)v16 + 1)] + (unsigned int)a1[4];
        if ( v9
          && RtlCompareUnicodeStrings(
               a2,
               v3,
               (PCWCH)((char *)a1 + *(unsigned int *)(v9 + 4)),
               (unsigned __int64)*(unsigned int *)(v9 + 12) >> 1,
               1u) )
        {
          return 0;
        }
        return v9;
      }
      v10 = v12 + 1;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1400077c0  push    rbx
0x1400077c2  push    rbp
0x1400077c3  push    rsi
0x1400077c4  push    r14
0x1400077c6  sub     rsp, 38h
0x1400077ca  movzx   ebp, r8w
0x1400077ce  xor     r10d, r10d
0x1400077d1  mov     r14, rdx
0x1400077d4  mov     rsi, rcx
0x1400077d7  test    ebp, ebp
0x1400077d9  jz      short loc_14000781F
0x1400077db  mov     [rsp+58h+arg_0], rdi
0x1400077e0  mov     r9, rdx
0x1400077e3  mov     edi, [rcx+18h]
0x1400077e6  xor     r11d, r11d
0x1400077e9  nop     dword ptr [rax+00000000h]
0x1400077f0  movzx   eax, word ptr [r9]
0x1400077f4  lea     ecx, [rax-41h]
0x1400077f7  cmp     cx, 19h
0x1400077fb  jbe     loc_1400078A7
0x140007801  mov     edx, edi
0x140007803  add     r9, 2
0x140007807  imul    edx, r10d
0x14000780b  inc     r11d
0x14000780e  movzx   r10d, ax
0x140007812  add     r10d, edx
0x140007815  cmp     r11d, ebp
0x140007818  jb      short loc_1400077F0
0x14000781a  mov     rdi, [rsp+58h+arg_0]
0x14000781f  mov     r9d, [rsi+0Ch]
0x140007823  xor     ebx, ebx
0x140007825  xor     r11d, r11d
0x140007828  dec     r9d
0x14000782b  nop     dword ptr [rax+rax+00h]
0x140007830  cmp     r11d, r9d
0x140007833  jg      short loc_1400078A2
0x140007835  mov     ecx, [rsi+14h]
0x140007838  lea     r8d, [r11+r9]
0x14000783c  sar     r8d, 1
0x14000783f  add     rcx, rsi
0x140007842  movsxd  rdx, r8d
0x140007845  cmp     r10d, [rcx+rdx*8]
0x140007849  lea     rcx, [rcx+rdx*8]
0x14000784d  jb      short loc_140007857
0x14000784f  jbe     short loc_14000785D
0x140007851  lea     r11d, [r8+1]
0x140007855  jmp     short loc_140007830
0x140007857  lea     r9d, [r8-1]
0x14000785b  jmp     short loc_140007830
0x14000785d  mov     eax, [rcx+4]
0x140007860  mov     ecx, [rsi+10h]
0x140007863  add     rcx, rsi
0x140007866  lea     rdx, [rax+rax*2]
0x14000786a  lea     rbx, [rcx+rdx*8]
0x14000786e  test    rbx, rbx
0x140007871  jz      short loc_1400078A2
0x140007873  mov     r9d, [rbx+0Ch]
0x140007877  mov     rdx, rbp; String1Length
0x14000787a  mov     r8d, [rbx+4]
0x14000787e  mov     rcx, r14; String1
0x140007881  shr     r9, 1; String2Length
0x140007884  add     r8, rsi; String2
0x140007887  mov     [rsp+58h+CaseInSensitive], 1; CaseInSensitive
0x14000788c  call    cs:__imp_RtlCompareUnicodeStrings
0x140007892  test    eax, eax
0x140007894  jz      short loc_1400078A2
0x140007896  xor     eax, eax
0x140007898  add     rsp, 38h
0x14000789c  pop     r14
0x14000789e  pop     rsi
0x14000789f  pop     rbp
0x1400078a0  pop     rbx
0x1400078a1  retn
0x1400078a2  mov     rax, rbx
0x1400078a5  jmp     short loc_140007898
0x1400078a7  add     ax, 20h ; ' '
0x1400078ab  jmp     loc_140007801
```

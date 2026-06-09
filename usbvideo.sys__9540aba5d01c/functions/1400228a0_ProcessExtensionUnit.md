# ProcessExtensionUnit

- ea: `0x1400228a0`
- end: `0x1400229aa`
- name: `ProcessExtensionUnit`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140021fb4`

## callees

- `0x140001544`
- `0x140018a70`
- `0x1400228a0`

## pseudocode

```c
__int64 __fastcall ProcessExtensionUnit(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        unsigned int *a6)
{
  int v6; // eax
  __int64 v10; // rcx
  unsigned int v11; // ebp
  __int64 v12; // rbx
  _DWORD *v13; // rdi
  char UnitControlInterface; // al
  __int64 v15; // rdx

  v6 = *a2;
  if ( (unsigned __int8)v6 >= 0x16u )
  {
    v10 = *(_QWORD *)(a1 + 16);
    v11 = *a6;
    v12 = 480LL * (unsigned int)*a5;
    v13 = (_DWORD *)(a4 + 16LL * *a6);
    *(_QWORD *)(v12 + a3 + 32) = a2;
    *(_QWORD *)(v12 + a3 + 8) = &KSNODETYPE_DEV_SPECIFIC;
    *(_QWORD *)(v12 + a3 + 16) = &KSNODETYPE_DEV_SPECIFIC;
    *(_DWORD *)(v12 + a3 + 44) = 9;
    *(_DWORD *)(v12 + a3 + 48) = 4097;
    UnitControlInterface = GetUnitControlInterface(v10, a2[3]);
    v15 = 0;
    for ( *(_BYTE *)(v12 + a3 + 40) = UnitControlInterface; (unsigned int)v15 < a2[21]; *(v13 - 1) = v15 )
    {
      ++v11;
      *v13 = a2[v15 + 22];
      v15 = (unsigned int)(v15 + 1);
      v13[1] = 0;
      v13 += 4;
      *(v13 - 2) = *a5;
    }
    *a6 = v11;
    ++*a5;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids,
        *(_QWORD *)(a1 + 16),
        a2,
        v6);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400228a0  push    rbx
0x1400228a2  push    rbp
0x1400228a3  push    rsi
0x1400228a4  push    rdi
0x1400228a5  push    r12
0x1400228a7  push    r14
0x1400228a9  push    r15
0x1400228ab  sub     rsp, 30h
0x1400228af  movzx   eax, byte ptr [rdx]
0x1400228b2  mov     r10, r9
0x1400228b5  mov     r9, [rcx+10h]
0x1400228b9  mov     r15, r8
0x1400228bc  mov     rsi, rdx
0x1400228bf  cmp     al, 16h
0x1400228c1  jnb     short loc_140022904
0x1400228c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400228ca  lea     rdx, WPP_GLOBAL_Control
0x1400228d1  cmp     rcx, rdx
0x1400228d4  jz      short loc_1400228FA
0x1400228d6  cmp     byte ptr [rcx+29h], 2
0x1400228da  jb      short loc_1400228FA
0x1400228dc  mov     rcx, [rcx+18h]
0x1400228e0  lea     r8, WPP_e64bf7c20dba36c8c56eb702b36d24e4_Traceguids
0x1400228e7  mov     [rsp+68h+var_40], eax
0x1400228eb  mov     edx, 12h
0x1400228f0  mov     [rsp+68h+var_48], rsi
0x1400228f5  call    WPP_SF_qqD
0x1400228fa  mov     eax, 0C000000Dh
0x1400228ff  jmp     loc_14002299A
0x140022904  mov     r14, [rsp+68h+arg_20]
0x14002290c  mov     rcx, r9
0x14002290f  mov     r12, [rsp+68h+arg_28]
0x140022917  mov     eax, [r14]
0x14002291a  mov     ebp, [r12]
0x14002291e  imul    rbx, rax, 1E0h
0x140022925  lea     rax, KSNODETYPE_DEV_SPECIFIC
0x14002292c  mov     edi, ebp
0x14002292e  shl     rdi, 4
0x140022932  add     rdi, r10
0x140022935  mov     [rbx+r8+20h], rsi
0x14002293a  mov     [rbx+r8+8], rax
0x14002293f  mov     [rbx+r8+10h], rax
0x140022944  mov     dword ptr [rbx+r8+2Ch], 9
0x14002294d  mov     dword ptr [rbx+r8+30h], 1001h
0x140022956  mov     dl, [rdx+3]
0x140022959  call    GetUnitControlInterface
0x14002295e  xor     edx, edx
0x140022960  mov     [rbx+r15+28h], al
0x140022965  cmp     [rsi+15h], dl
0x140022968  jbe     short loc_140022991
0x14002296a  movzx   ecx, byte ptr [rdx+rsi+16h]
0x14002296f  inc     ebp
0x140022971  mov     [rdi], ecx
0x140022973  inc     edx
0x140022975  mov     dword ptr [rdi+4], 0
0x14002297c  lea     rdi, [rdi+10h]
0x140022980  mov     eax, [r14]
0x140022983  mov     [rdi-8], eax
0x140022986  mov     [rdi-4], edx
0x140022989  movzx   eax, byte ptr [rsi+15h]
0x14002298d  cmp     edx, eax
0x14002298f  jb      short loc_14002296A
0x140022991  mov     [r12], ebp
0x140022995  inc     dword ptr [r14]
0x140022998  xor     eax, eax
0x14002299a  add     rsp, 30h
0x14002299e  pop     r15
0x1400229a0  pop     r14
0x1400229a2  pop     r12
0x1400229a4  pop     rdi
0x1400229a5  pop     rsi
0x1400229a6  pop     rbp
0x1400229a7  pop     rbx
0x1400229a8  retn
```

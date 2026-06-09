# MTX_AGFACOMP_UnPack_TTF_InMemory

- ea: `0x18000de70`
- end: `0x18000e125`
- name: `MTX_AGFACOMP_UnPack_TTF_InMemory`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001a414`

## callees

- `0x180006548`
- `0x180009c80`
- `0x18000dca8`
- `0x18000de70`
- `0x18000e580`
- `0x18000e5e4`
- `0x18001c574`
- `0x18001c9ec`
- `0x18001d35c`
- `0x18002b010`

## import_xrefs

- `msvcrt!longjmp` at `0x18000deb6`
- `msvcrt!longjmp` at `0x18000ded4`
- `msvcrt!longjmp` at `0x18000deb6`
- `msvcrt!longjmp` at `0x18000ded4`

## pseudocode

```c
__int64 __fastcall MTX_AGFACOMP_UnPack_TTF_InMemory(
        __int64 a1,
        unsigned __int8 *a2,
        unsigned int a3,
        _DWORD *a4,
        _DWORD *a5)
{
  __int64 v6; // rbx
  unsigned __int16 v8; // r15
  unsigned __int8 *v9; // r12
  unsigned int v10; // r13d
  unsigned __int8 *v11; // rsi
  unsigned __int64 v12; // r14
  unsigned __int8 *v13; // r14
  __int64 v14; // rbx
  __int64 v15; // r12
  __int64 v16; // rbx
  int v17; // esi
  __int64 v18; // rbx
  __int64 v19; // r14
  __int64 v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rsi
  int v24; // [rsp+40h] [rbp-68h] BYREF
  int v25; // [rsp+44h] [rbp-64h] BYREF
  int v26; // [rsp+48h] [rbp-60h] BYREF
  int v27; // [rsp+4Ch] [rbp-5Ch]
  __int64 v28; // [rsp+50h] [rbp-58h]
  int v29; // [rsp+58h] [rbp-50h]

  v6 = (int)a3;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  if ( !(unsigned int)MTX_IS_MTX_Data(a2, a3) )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 64) + 48LL), 3360);
  v8 = *a2;
  if ( (unsigned __int8)v8 > 3u )
    longjmp((_JBTYPE *)(*(_QWORD *)(a1 + 64) + 48LL), 3302);
  v9 = a2 + 10;
  v10 = a2[3] | ((a2[2] | (a2[1] << 8)) << 8);
  v11 = &a2[a2[6] | ((a2[5] | ((unsigned __int64)a2[4] << 8)) << 8)];
  v12 = a2[9] | ((a2[8] | ((unsigned __int64)a2[7] << 8)) << 8);
  v27 = (a2[6] | ((a2[5] | (a2[4] << 8)) << 8)) - 10;
  v13 = &a2[v12];
  LODWORD(v28) = (_DWORD)v13 - (_DWORD)v11;
  v29 = v6 + (_DWORD)a2 - (_DWORD)v13;
  if ( v27 < 0 || (int)v13 - (int)v11 < 0 || (int)v6 + (int)a2 - (int)v13 < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( v9 <= a2 || v9 >= &a2[v6] )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( v11 <= a2 || v11 > &a2[v6] )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( v13 <= a2 || v13 > &a2[v6] )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v14 = MTX_LZCOMP_Create2(*(_QWORD *)(a1 + 64), v10);
  v15 = MTX_LZCOMP_UnPackMemory(v14, (int)a2 + 10, v27, (unsigned int)&v26, v8);
  MTX_LZCOMP_Destroy(v14);
  v16 = MTX_LZCOMP_Create2(*(_QWORD *)(a1 + 64), v10);
  v28 = MTX_LZCOMP_UnPackMemory(v16, (_DWORD)v11, v28, (unsigned int)&v25, v8);
  v17 = v28;
  MTX_LZCOMP_Destroy(v16);
  v18 = MTX_LZCOMP_Create2(*(_QWORD *)(a1 + 64), v10);
  v19 = MTX_LZCOMP_UnPackMemory(v18, (_DWORD)v13, v29, (unsigned int)&v24, v8);
  MTX_LZCOMP_Destroy(v18);
  if ( *a4 )
  {
    if ( *a4 == 2 )
    {
      (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)(a1 + 64) + 40LL))(a2);
    }
    else
    {
      if ( *a4 != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      DiscardPointer(*(_QWORD *)(a1 + 64), a2, 1);
    }
    *a4 = 0;
  }
  v20 = MTX_TTC_Create(*(_QWORD *)(a1 + 64), v8);
  v21 = MTX_TTC_CTF_To_TTF(v20, v15, v26, v17, v25, v19, v24, (__int64)a5);
  *(_DWORD *)(a1 + 4) = *a5;
  v22 = v21;
  DiscardPointer(*(_QWORD *)(v20 + 96), v20, 1);
  DiscardPointer(*(_QWORD *)(a1 + 64), v15, 1);
  DiscardPointer(*(_QWORD *)(a1 + 64), v28, 1);
  DiscardPointer(*(_QWORD *)(a1 + 64), v19, 1);
  return v22;
}

```

## disassembly

```asm
0x18000de70  mov     rax, rsp
0x18000de73  mov     [rax+20h], r9
0x18000de77  push    rbx
0x18000de78  push    rbp
0x18000de79  push    rsi
0x18000de7a  push    rdi
0x18000de7b  push    r12
0x18000de7d  push    r13
0x18000de7f  push    r14
0x18000de81  push    r15
0x18000de83  sub     rsp, 68h
0x18000de87  mov     rdi, rdx
0x18000de8a  movsxd  rbx, r8d
0x18000de8d  xor     esi, esi
0x18000de8f  mov     rbp, rcx
0x18000de92  mov     edx, ebx
0x18000de94  mov     [rax-60h], esi
0x18000de97  mov     rcx, rdi
0x18000de9a  mov     [rax-64h], esi
0x18000de9d  mov     [rax-68h], esi
0x18000dea0  call    MTX_IS_MTX_Data
0x18000dea5  test    eax, eax
0x18000dea7  jnz     short loc_18000DEBD
0x18000dea9  mov     rcx, [rbp+40h]
0x18000dead  mov     edx, 0D20h; Value
0x18000deb2  add     rcx, 30h ; '0'; Buf
0x18000deb6  call    cs:__imp_longjmp
0x18000debd  movzx   r15d, byte ptr [rdi]
0x18000dec1  cmp     r15b, 3
0x18000dec5  jbe     short loc_18000DEDB
0x18000dec7  mov     rcx, [rbp+40h]
0x18000decb  mov     edx, 0CE6h; Value
0x18000ded0  add     rcx, 30h ; '0'; Buf
0x18000ded4  call    cs:__imp_longjmp
0x18000dedb  movzx   eax, byte ptr [rdi+2]
0x18000dedf  lea     r12, [rdi+0Ah]
0x18000dee3  movzx   r13d, byte ptr [rdi+1]
0x18000dee8  movzx   esi, byte ptr [rdi+4]
0x18000deec  movzx   r14d, byte ptr [rdi+7]
0x18000def1  shl     rsi, 8
0x18000def5  shl     r14, 8
0x18000def9  shl     r13d, 8
0x18000defd  or      r13d, eax
0x18000df00  movzx   eax, byte ptr [rdi+3]
0x18000df04  shl     r13d, 8
0x18000df08  or      r13d, eax
0x18000df0b  movzx   eax, byte ptr [rdi+5]
0x18000df0f  or      rsi, rax
0x18000df12  movzx   eax, byte ptr [rdi+6]
0x18000df16  shl     rsi, 8
0x18000df1a  or      rsi, rax
0x18000df1d  movzx   eax, byte ptr [rdi+8]
0x18000df21  or      r14, rax
0x18000df24  add     rsi, rdi
0x18000df27  movzx   eax, byte ptr [rdi+9]
0x18000df2b  mov     edx, esi
0x18000df2d  shl     r14, 8
0x18000df31  sub     edx, r12d
0x18000df34  or      r14, rax
0x18000df37  mov     [rsp+0A8h+var_5C], edx
0x18000df3b  add     r14, rdi
0x18000df3e  mov     eax, edi
0x18000df40  sub     eax, r14d
0x18000df43  mov     ecx, r14d
0x18000df46  sub     ecx, esi
0x18000df48  add     eax, ebx
0x18000df4a  mov     dword ptr [rsp+0A8h+var_58], ecx
0x18000df4e  mov     [rsp+0A8h+var_50], eax
0x18000df52  test    edx, edx
0x18000df54  js      short loc_18000DF5E
0x18000df56  test    ecx, ecx
0x18000df58  js      short loc_18000DF5E
0x18000df5a  test    eax, eax
0x18000df5c  jns     short loc_18000DF63
0x18000df5e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000df63  cmp     r12, rdi
0x18000df66  jbe     short loc_18000DF71
0x18000df68  lea     rax, [rbx+rdi]
0x18000df6c  cmp     r12, rax
0x18000df6f  jb      short loc_18000DF76
0x18000df71  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000df76  cmp     rsi, rdi
0x18000df79  jbe     short loc_18000DF84
0x18000df7b  lea     rax, [rbx+rdi]
0x18000df7f  cmp     rsi, rax
0x18000df82  jbe     short loc_18000DF89
0x18000df84  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000df89  cmp     r14, rdi
0x18000df8c  jbe     short loc_18000DF97
0x18000df8e  lea     rax, [rbx+rdi]
0x18000df92  cmp     r14, rax
0x18000df95  jbe     short loc_18000DF9C
0x18000df97  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000df9c  mov     rcx, [rbp+40h]
0x18000dfa0  mov     edx, r13d
0x18000dfa3  call    MTX_LZCOMP_Create2
0x18000dfa8  mov     r8d, [rsp+0A8h+var_5C]
0x18000dfad  lea     r9, [rsp+0A8h+var_60]
0x18000dfb2  mov     rdx, r12
0x18000dfb5  mov     byte ptr [rsp+0A8h+var_88], r15b
0x18000dfba  mov     rcx, rax
0x18000dfbd  mov     rbx, rax
0x18000dfc0  call    MTX_LZCOMP_UnPackMemory
0x18000dfc5  mov     rcx, rbx
0x18000dfc8  mov     r12, rax
0x18000dfcb  call    MTX_LZCOMP_Destroy
0x18000dfd0  mov     rcx, [rbp+40h]
0x18000dfd4  mov     edx, r13d
0x18000dfd7  call    MTX_LZCOMP_Create2
0x18000dfdc  mov     r8d, dword ptr [rsp+0A8h+var_58]
0x18000dfe1  lea     r9, [rsp+0A8h+var_64]
0x18000dfe6  mov     rdx, rsi
0x18000dfe9  mov     byte ptr [rsp+0A8h+var_88], r15b
0x18000dfee  mov     rcx, rax
0x18000dff1  mov     rbx, rax
0x18000dff4  call    MTX_LZCOMP_UnPackMemory
0x18000dff9  mov     rcx, rbx
0x18000dffc  mov     [rsp+0A8h+var_58], rax
0x18000e001  mov     rsi, rax
0x18000e004  call    MTX_LZCOMP_Destroy
0x18000e009  mov     rcx, [rbp+40h]
0x18000e00d  mov     edx, r13d
0x18000e010  call    MTX_LZCOMP_Create2
0x18000e015  mov     r8d, [rsp+0A8h+var_50]
0x18000e01a  lea     r9, [rsp+0A8h+var_68]
0x18000e01f  mov     rdx, r14
0x18000e022  mov     byte ptr [rsp+0A8h+var_88], r15b
0x18000e027  mov     rcx, rax
0x18000e02a  mov     rbx, rax
0x18000e02d  call    MTX_LZCOMP_UnPackMemory
0x18000e032  mov     rcx, rbx
0x18000e035  mov     r14, rax
0x18000e038  call    MTX_LZCOMP_Destroy
0x18000e03d  mov     rbx, [rsp+0A8h+arg_18]
0x18000e045  mov     r13d, 1
0x18000e04b  cmp     dword ptr [rbx], 0
0x18000e04e  jz      short loc_18000E086
0x18000e050  cmp     dword ptr [rbx], 2
0x18000e053  jnz     short loc_18000E067
0x18000e055  mov     rcx, [rbp+40h]
0x18000e059  mov     rax, [rcx+28h]
0x18000e05d  mov     rcx, rdi
0x18000e060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e065  jmp     short loc_18000E080
0x18000e067  cmp     [rbx], r13d
0x18000e06a  jz      short loc_18000E071
0x18000e06c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e071  mov     rcx, [rbp+40h]
0x18000e075  mov     r8d, r13d
0x18000e078  mov     rdx, rdi
0x18000e07b  call    DiscardPointer
0x18000e080  mov     dword ptr [rbx], 0
0x18000e086  mov     rcx, [rbp+40h]
0x18000e08a  movzx   edx, r15w
0x18000e08e  call    MTX_TTC_Create
0x18000e093  mov     ecx, [rsp+0A8h+var_68]
0x18000e097  mov     r9, rsi
0x18000e09a  mov     rbx, [rsp+0A8h+arg_20]
0x18000e0a2  mov     rdx, r12
0x18000e0a5  mov     r8d, [rsp+0A8h+var_60]
0x18000e0aa  mov     rdi, rax
0x18000e0ad  mov     [rsp+0A8h+var_70], rbx
0x18000e0b2  mov     [rsp+0A8h+var_78], ecx
0x18000e0b6  mov     ecx, [rsp+0A8h+var_64]
0x18000e0ba  mov     [rsp+0A8h+var_80], r14
0x18000e0bf  mov     [rsp+0A8h+var_88], ecx
0x18000e0c3  mov     rcx, rax
0x18000e0c6  call    MTX_TTC_CTF_To_TTF
0x18000e0cb  mov     ecx, [rbx]
0x18000e0cd  mov     r8d, r13d
0x18000e0d0  mov     [rbp+4], ecx
0x18000e0d3  mov     rdx, rdi
0x18000e0d6  mov     rcx, [rdi+60h]
0x18000e0da  mov     rsi, rax
0x18000e0dd  call    DiscardPointer
0x18000e0e2  mov     rcx, [rbp+40h]
0x18000e0e6  mov     r8d, r13d
0x18000e0e9  mov     rdx, r12
0x18000e0ec  call    DiscardPointer
0x18000e0f1  mov     rdx, [rsp+0A8h+var_58]
0x18000e0f6  mov     r8d, r13d
0x18000e0f9  mov     rcx, [rbp+40h]
0x18000e0fd  call    DiscardPointer
0x18000e102  mov     rcx, [rbp+40h]
0x18000e106  mov     r8d, r13d
0x18000e109  mov     rdx, r14
0x18000e10c  call    DiscardPointer
0x18000e111  mov     rax, rsi
0x18000e114  add     rsp, 68h
0x18000e118  pop     r15
0x18000e11a  pop     r14
0x18000e11c  pop     r13
0x18000e11e  pop     r12
0x18000e120  pop     rdi
0x18000e121  pop     rsi
0x18000e122  pop     rbp
0x18000e123  pop     rbx
0x18000e124  retn
```

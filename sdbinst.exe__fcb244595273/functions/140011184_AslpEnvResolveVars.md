# AslpEnvResolveVars

- ea: `0x140011184`
- end: `0x1400114c6`
- name: `AslpEnvResolveVars`
- size: `834`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16, unsigned __int16, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000ee5c`

## callees

- `0x14000acf4`
- `0x14001008c`
- `0x140011184`
- `0x140011d6c`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1400111e6`
- `msvcrt!_wcsnicmp` at `0x1400111e6`

## string_xrefs

- `0x140011428`: `RtlStringCchCopyW failed [%x]`
- `0x14001143b`: `RtlStringCchCopyW failed [%x]`
- `0x140011494`: `RtlStringCchCopyW failed [%x]`
- `0x14001144f`: `ResolvedPath is NULL or zero size [%#x]`
- `0x140011319`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`

## pseudocode

```c
__int64 __fastcall AslpEnvResolveVars(
        const wchar_t *a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        unsigned int *a7)
{
  int v7; // ebx
  __int64 v8; // r14
  int v9; // r13d
  unsigned int v10; // esi
  unsigned __int16 *v11; // rdi
  __int64 v12; // r12
  __int64 v14; // r15
  unsigned int v15; // eax
  unsigned __int16 v16; // cx
  unsigned __int64 i; // rdi
  unsigned __int16 v18; // ax
  int v19; // eax
  __int64 v20; // r11
  unsigned int v21; // ebx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v28; // [rsp+20h] [rbp-48h]
  const wchar_t *v29; // [rsp+70h] [rbp+8h]

  v29 = a1;
  v7 = 0;
  v8 = a4;
  v9 = 0;
  v10 = 0;
  v11 = a3;
  v12 = 0;
  while ( !v7 )
  {
    v14 = 3 * v12;
    v15 = qword_1400420D0[3 * v12];
    if ( a2 > v15 )
    {
      if ( !_wcsnicmp(a1, off_1400420C0[v14], v15) )
      {
        v10 = a2 + HIDWORD(qword_1400420D0[v14]) - LODWORD(qword_1400420D0[v14]);
        if ( v10 > (unsigned int)v8 )
        {
          v21 = -1073741789;
          goto LABEL_39;
        }
        if ( !v11 || !(_DWORD)v8 )
        {
          v21 = -1073741811;
          LODWORD(v28) = -1073741811;
          AslLogCallPrintf(1, "AslpEnvResolveVars", 1035, "ResolvedPath is NULL or zero size [%#x]", v28);
          return v21;
        }
        if ( v12 )
        {
          if ( !v9 )
          {
LABEL_20:
            v24 = RtlStringCchCopyW(v11, v8, (&off_1400420C8)[v14]);
            v21 = v24;
            if ( v24 < 0 )
            {
              LODWORD(v28) = v24;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1091, "RtlStringCchCopyW failed [%x]", v28);
              return v21;
            }
            v25 = RtlStringCchCatW(v11, v8, (unsigned __int16 *)&v29[LODWORD(qword_1400420D0[v14])]);
            v21 = v25;
            if ( v25 < 0 )
            {
              LODWORD(v28) = v25;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1097, "RtlStringCchCatW failed [%x]", v28);
              return v21;
            }
          }
        }
        else
        {
          v16 = a5;
          for ( i = 0; i < 8; ++i )
          {
            v18 = a6;
            if ( word_140042040[8 * i] == v16 && word_140042042[8 * i] == a6 )
            {
              v19 = RtlStringCchCopyW(a3, v8, L"%systemroot%");
              v21 = v19;
              if ( v19 < 0 )
              {
                LODWORD(v28) = v19;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1051, "RtlStringCchCopyW failed [%x]", v28);
                return v21;
              }
              v22 = RtlStringCchCatW(a3, v8, (&off_140042048)[v20]);
              v21 = v22;
              if ( v22 < 0 )
              {
                LODWORD(v28) = v22;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1057, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v23 = RtlStringCchCatW(a3, v8, (unsigned __int16 *)&v29[LODWORD(qword_1400420D0[v14])]);
              v21 = v23;
              if ( v23 < 0 )
              {
                LODWORD(v28) = v23;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1063, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v18 = a6;
              v16 = a5;
              v9 = 1;
            }
          }
          if ( !v9 )
          {
            AslLogCallPrintf(
              1,
              "AslpEnvResolveVars",
              1074,
              "Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4",
              v16,
              v18);
            v11 = a3;
            goto LABEL_20;
          }
          v11 = a3;
        }
        v7 = 1;
      }
      a1 = v29;
    }
    if ( (unsigned __int64)++v12 >= 4 )
    {
      if ( !v7 )
      {
        if ( a2 > (unsigned int)v8 )
        {
          v21 = -1073741789;
          *a7 = a2;
          return v21;
        }
        v10 = a2;
        v26 = RtlStringCchCopyW(v11, v8, a1);
        v21 = v26;
        if ( v26 < 0 )
        {
          LODWORD(v28) = v26;
          AslLogCallPrintf(1, "AslpEnvResolveVars", 1129, "RtlStringCchCopyW failed [%x]", v28);
          return v21;
        }
      }
      break;
    }
  }
  v21 = 0;
LABEL_39:
  *a7 = v10;
  return v21;
}

```

## disassembly

```asm
0x140011184  mov     [rsp+arg_8], rbx
0x140011189  mov     [rsp+arg_10], r8
0x14001118e  mov     [rsp+arg_0], rcx
0x140011193  push    rbp
0x140011194  push    rsi
0x140011195  push    rdi
0x140011196  push    r12
0x140011198  push    r13
0x14001119a  push    r14
0x14001119c  push    r15
0x14001119e  sub     rsp, 30h
0x1400111a2  xor     ebx, ebx
0x1400111a4  mov     r14d, r9d
0x1400111a7  xor     r13d, r13d
0x1400111aa  lea     r11, cs:140000000h
0x1400111b1  xor     esi, esi
0x1400111b3  mov     rdi, r8
0x1400111b6  xor     r12d, r12d
0x1400111b9  mov     ebp, edx
0x1400111bb  test    ebx, ebx
0x1400111bd  jnz     loc_1400114A3
0x1400111c3  lea     r15, [r12+r12*2]
0x1400111c7  shl     r15, 3
0x1400111cb  mov     eax, [r15+r11+420D0h]
0x1400111d3  cmp     ebp, eax
0x1400111d5  jbe     loc_1400113CC
0x1400111db  mov     rdx, [r15+r11+420C0h]; String2
0x1400111e3  mov     r8d, eax; MaxCount
0x1400111e6  call    cs:__imp__wcsnicmp
0x1400111ec  lea     r11, cs:140000000h
0x1400111f3  test    eax, eax
0x1400111f5  jnz     loc_1400113C7
0x1400111fb  mov     esi, [r15+r11+420D4h]
0x140011203  sub     esi, [r15+r11+420D0h]
0x14001120b  add     esi, ebp
0x14001120d  cmp     esi, r14d
0x140011210  ja      loc_140011473
0x140011216  test    rdi, rdi
0x140011219  jz      loc_14001144A
0x14001121f  test    r14d, r14d
0x140011222  jz      loc_14001144A
0x140011228  test    r12, r12
0x14001122b  jnz     loc_14001134B
0x140011231  movzx   ecx, [rsp+68h+arg_20]
0x140011239  lea     rdx, cs:140000000h
0x140011240  xor     edi, edi
0x140011242  movzx   eax, [rsp+68h+arg_28]
0x14001124a  mov     r11, rdi
0x14001124d  add     r11, r11
0x140011250  cmp     rva word_140042040[rdx+r11*8], cx
0x140011259  jnz     loc_140011300
0x14001125f  cmp     rva word_140042042[rdx+r11*8], ax
0x140011268  jnz     loc_140011300
0x14001126e  mov     r13, [rsp+68h+arg_10]
0x140011276  lea     r8, aSystemroot; "%systemroot%"
0x14001127d  mov     rcx, r13
0x140011280  mov     rdx, r14
0x140011283  call    RtlStringCchCopyW
0x140011288  mov     ebx, eax
0x14001128a  test    eax, eax
0x14001128c  js      loc_140011424
0x140011292  lea     r8, cs:140000000h
0x140011299  mov     rdx, r14; unsigned __int64
0x14001129c  mov     r8, rva off_140042048[r8+r11*8]; unsigned __int16 *
0x1400112a4  mov     rcx, r13; unsigned __int16 *
0x1400112a7  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400112ac  mov     ebx, eax
0x1400112ae  test    eax, eax
0x1400112b0  js      loc_140011411
0x1400112b6  mov     rcx, [rsp+68h+arg_0]
0x1400112bb  lea     rax, cs:140000000h
0x1400112c2  mov     eax, [r15+rax+420D0h]
0x1400112ca  mov     rdx, r14; unsigned __int64
0x1400112cd  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x1400112d1  mov     rcx, r13; unsigned __int16 *
0x1400112d4  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400112d9  mov     ebx, eax
0x1400112db  test    eax, eax
0x1400112dd  js      loc_1400113FE
0x1400112e3  movzx   eax, [rsp+68h+arg_28]
0x1400112eb  lea     rdx, cs:140000000h
0x1400112f2  movzx   ecx, [rsp+68h+arg_20]
0x1400112fa  mov     r13d, 1
0x140011300  inc     rdi
0x140011303  cmp     rdi, 8
0x140011307  jb      loc_140011242
0x14001130d  test    r13d, r13d
0x140011310  jnz     loc_1400113B3
0x140011316  movzx   ecx, cx
0x140011319  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x140011320  movzx   eax, ax
0x140011323  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x14001132a  mov     [rsp+68h+var_40], eax
0x14001132e  mov     r8d, 432h
0x140011334  mov     dword ptr [rsp+68h+var_48], ecx
0x140011338  lea     ecx, [r13+1]
0x14001133c  call    AslLogCallPrintf
0x140011341  mov     rdi, [rsp+68h+arg_10]
0x140011349  jmp     short loc_140011350
0x14001134b  test    r13d, r13d
0x14001134e  jnz     short loc_1400113C2
0x140011350  lea     rax, cs:140000000h
0x140011357  mov     rdx, r14
0x14001135a  mov     r8, [r15+rax+420C8h]
0x140011362  mov     rcx, rdi
0x140011365  call    RtlStringCchCopyW
0x14001136a  mov     ebx, eax
0x14001136c  test    eax, eax
0x14001136e  js      loc_140011437
0x140011374  mov     rcx, [rsp+68h+arg_0]
0x140011379  lea     rax, cs:140000000h
0x140011380  mov     eax, [r15+rax+420D0h]
0x140011388  mov     rdx, r14; unsigned __int64
0x14001138b  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x14001138f  mov     rcx, rdi; unsigned __int16 *
0x140011392  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140011397  mov     ebx, eax
0x140011399  test    eax, eax
0x14001139b  jns     short loc_1400113BB
0x14001139d  mov     dword ptr [rsp+68h+var_48], eax
0x1400113a1  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x1400113a8  mov     r8d, 449h
0x1400113ae  jmp     loc_140011460
0x1400113b3  mov     rdi, [rsp+68h+arg_10]
0x1400113bb  lea     r11, cs:140000000h
0x1400113c2  mov     ebx, 1
0x1400113c7  mov     rcx, [rsp+68h+arg_0]
0x1400113cc  inc     r12
0x1400113cf  cmp     r12, 4
0x1400113d3  jb      loc_1400111BB
0x1400113d9  test    ebx, ebx
0x1400113db  jnz     loc_1400114A3
0x1400113e1  cmp     ebp, r14d
0x1400113e4  jbe     loc_14001147A
0x1400113ea  mov     rax, [rsp+68h+arg_30]
0x1400113f2  mov     ebx, 0C0000023h
0x1400113f7  mov     [rax], ebp
0x1400113f9  jmp     loc_1400114AF
0x1400113fe  mov     dword ptr [rsp+68h+var_48], eax
0x140011402  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x140011409  mov     r8d, 427h
0x14001140f  jmp     short loc_140011460
0x140011411  mov     dword ptr [rsp+68h+var_48], eax
0x140011415  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14001141c  mov     r8d, 421h
0x140011422  jmp     short loc_140011460
0x140011424  mov     dword ptr [rsp+68h+var_48], eax
0x140011428  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14001142f  mov     r8d, 41Bh
0x140011435  jmp     short loc_140011460
0x140011437  mov     dword ptr [rsp+68h+var_48], eax
0x14001143b  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140011442  mov     r8d, 443h
0x140011448  jmp     short loc_140011460
0x14001144a  mov     ebx, 0C000000Dh
0x14001144f  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x140011456  mov     dword ptr [rsp+68h+var_48], ebx
0x14001145a  mov     r8d, 40Bh
0x140011460  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x140011467  mov     ecx, 1
0x14001146c  call    AslLogCallPrintf
0x140011471  jmp     short loc_1400114AF
0x140011473  mov     ebx, 0C0000023h
0x140011478  jmp     short loc_1400114A5
0x14001147a  mov     r8, rcx
0x14001147d  mov     rdx, r14
0x140011480  mov     rcx, rdi
0x140011483  mov     esi, ebp
0x140011485  call    RtlStringCchCopyW
0x14001148a  mov     ebx, eax
0x14001148c  test    eax, eax
0x14001148e  jns     short loc_1400114A3
0x140011490  mov     dword ptr [rsp+68h+var_48], eax
0x140011494  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14001149b  mov     r8d, 469h
0x1400114a1  jmp     short loc_140011460
0x1400114a3  xor     ebx, ebx
0x1400114a5  mov     rax, [rsp+68h+arg_30]
0x1400114ad  mov     [rax], esi
0x1400114af  mov     eax, ebx
0x1400114b1  mov     rbx, [rsp+68h+arg_8]
0x1400114b6  add     rsp, 30h
0x1400114ba  pop     r15
0x1400114bc  pop     r14
0x1400114be  pop     r13
0x1400114c0  pop     r12
0x1400114c2  pop     rdi
0x1400114c3  pop     rsi
0x1400114c4  pop     rbp
0x1400114c5  retn
```

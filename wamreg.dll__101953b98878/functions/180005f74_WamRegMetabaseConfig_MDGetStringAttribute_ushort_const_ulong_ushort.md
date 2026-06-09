# WamRegMetabaseConfig::MDGetStringAttribute(ushort const *,ulong,ushort * *)

- ea: `0x180005f74`
- end: `0x1800060ec`
- name: `?MDGetStringAttribute@WamRegMetabaseConfig@@QEAAJPEBGKPEAPEAG@Z`
- size: `376`
- prototype: `__int64 __fastcall(WamRegMetabaseConfig *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000368c`
- `0x180003b30`
- `0x180003d80`

## callees

- `0x180001044`
- `0x180001084`
- `0x180005f74`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall WamRegMetabaseConfig::MDGetStringAttribute(
        WamRegMetabaseConfig *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int16 **a4)
{
  LPVOID v4; // rcx
  void *v5; // rdi
  int v8; // ebx
  int v9; // eax
  void *v10; // rax
  __int128 v12; // [rsp+40h] [rbp-30h] BYREF
  __int128 v13; // [rsp+50h] [rbp-20h]
  __int64 v14; // [rsp+60h] [rbp-10h]
  unsigned int v15; // [rsp+90h] [rbp+20h] BYREF
  int v16; // [rsp+94h] [rbp+24h]
  unsigned int v17; // [rsp+A8h] [rbp+38h] BYREF

  v16 = HIDWORD(this);
  v4 = WamRegMetabaseConfig::m_pMetabase;
  *a4 = 0;
  v5 = 0;
  v14 = 0;
  v15 = 0;
  v17 = 0;
  v12 = 0;
  v13 = 0;
  v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const unsigned __int16 *, __int64, int, unsigned int *))(*(_QWORD *)v4 + 136LL))(
         v4,
         0,
         a2,
         1,
         30000,
         &v17);
  if ( v8 < 0 )
    goto LABEL_10;
  LODWORD(v12) = a3;
  LODWORD(v13) = v15;
  *(_QWORD *)((char *)&v12 + 4) = 0x6400000001LL;
  HIDWORD(v12) = 2;
  *((_QWORD *)&v13 + 1) = 0;
  v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int128 *, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                                     + 80LL))(
         WamRegMetabaseConfig::m_pMetabase,
         v17,
         0,
         &v12,
         &v15);
  v9 = (unsigned __int16)v8;
  if ( (v8 & 0x1FFF0000) != 0x70000 )
    v9 = v8;
  if ( v9 == 122 )
  {
    v10 = operator new(saturated_mul((unsigned __int64)v15 >> 1, 2u));
    v5 = v10;
    if ( v10 )
    {
      LODWORD(v13) = v15;
      *((_QWORD *)&v13 + 1) = v10;
      v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int128 *, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                                         + 80LL))(
             WamRegMetabaseConfig::m_pMetabase,
             v17,
             0,
             &v12,
             &v15);
    }
    else
    {
      v8 = -2147024882;
    }
  }
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 144LL))(
    WamRegMetabaseConfig::m_pMetabase,
    v17);
  if ( v8 < 0 )
LABEL_10:
    operator delete(v5);
  else
    *a4 = (unsigned __int16 *)v5;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005f74  mov     r11, rsp
0x180005f77  mov     [r11+10h], rbx
0x180005f7b  mov     [r11+18h], rsi
0x180005f7f  mov     [r11+8], rcx
0x180005f83  push    rbp
0x180005f84  push    rdi
0x180005f85  push    r14
0x180005f87  mov     rbp, rsp
0x180005f8a  sub     rsp, 70h
0x180005f8e  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005f95  xor     eax, eax
0x180005f97  mov     [r9], rax
0x180005f9a  xor     edi, edi
0x180005f9c  xorps   xmm0, xmm0
0x180005f9f  mov     [rbp+var_10], rax
0x180005fa3  mov     r14d, r8d
0x180005fa6  mov     [rbp+arg_0], edi
0x180005fa9  mov     [rbp+arg_18], edi
0x180005fac  lea     r8, [rbp+arg_18]
0x180005fb0  mov     [r11-60h], r8
0x180005fb4  mov     rsi, r9
0x180005fb7  movups  [rbp+var_30], xmm0
0x180005fbb  mov     r8, rdx
0x180005fbe  lea     r9d, [rdi+1]
0x180005fc2  movups  [rbp+var_20], xmm0
0x180005fc6  mov     rax, [rcx]
0x180005fc9  xor     edx, edx
0x180005fcb  mov     dword ptr [rsp+70h+var_50], 7530h
0x180005fd3  mov     rax, [rax+88h]
0x180005fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fdf  mov     ebx, eax
0x180005fe1  test    eax, eax
0x180005fe3  js      loc_1800060CD
0x180005fe9  mov     eax, [rbp+arg_0]
0x180005fec  lea     rdx, [rbp+arg_0]
0x180005ff0  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005ff7  lea     r9, [rbp+var_30]
0x180005ffb  mov     dword ptr [rbp+var_30], r14d
0x180005fff  xor     r8d, r8d
0x180006002  mov     dword ptr [rbp+var_20], eax
0x180006005  lea     r14d, [rdi+2]
0x180006009  mov     dword ptr [rbp+var_30+4], 1
0x180006010  mov     dword ptr [rbp+var_30+8], 64h ; 'd'
0x180006017  mov     dword ptr [rbp+var_30+0Ch], r14d
0x18000601b  mov     qword ptr [rbp+var_20+8], rdi
0x18000601f  mov     rax, [rcx]
0x180006022  mov     [rsp+70h+var_50], rdx
0x180006027  mov     edx, [rbp+arg_18]
0x18000602a  mov     rax, [rax+50h]
0x18000602e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006033  mov     ebx, eax
0x180006035  and     eax, 1FFF0000h
0x18000603a  cmp     eax, 70000h
0x18000603f  movzx   eax, bx
0x180006042  jz      short loc_180006046
0x180006044  mov     eax, ebx
0x180006046  cmp     eax, 7Ah ; 'z'
0x180006049  jnz     short loc_1800060AB
0x18000604b  mov     ecx, [rbp+arg_0]
0x18000604e  mov     rax, r14
0x180006051  shr     rcx, 1
0x180006054  mul     rcx
0x180006057  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000605e  cmovb   rax, rcx
0x180006062  mov     rcx, rax; Size
0x180006065  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000606a  mov     rdi, rax
0x18000606d  test    rax, rax
0x180006070  jz      short loc_1800060A6
0x180006072  mov     ecx, [rbp+arg_0]
0x180006075  lea     r9, [rbp+var_30]
0x180006079  mov     dword ptr [rbp+var_20], ecx
0x18000607c  xor     r8d, r8d
0x18000607f  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180006086  mov     qword ptr [rbp+var_20+8], rax
0x18000608a  mov     rdx, [rcx]
0x18000608d  mov     rax, [rdx+50h]
0x180006091  lea     rdx, [rbp+arg_0]
0x180006095  mov     [rsp+70h+var_50], rdx
0x18000609a  mov     edx, [rbp+arg_18]
0x18000609d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a2  mov     ebx, eax
0x1800060a4  jmp     short loc_1800060AB
0x1800060a6  mov     ebx, 8007000Eh
0x1800060ab  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800060b2  mov     edx, [rbp+arg_18]
0x1800060b5  mov     rax, [rcx]
0x1800060b8  mov     rax, [rax+90h]
0x1800060bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c4  test    ebx, ebx
0x1800060c6  js      short loc_1800060CD
0x1800060c8  mov     [rsi], rdi
0x1800060cb  jmp     short loc_1800060D5
0x1800060cd  mov     rcx, rdi; Block
0x1800060d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800060d5  lea     r11, [rsp+70h+var_s0]
0x1800060da  mov     eax, ebx
0x1800060dc  mov     rbx, [r11+28h]
0x1800060e0  mov     rsi, [r11+30h]
0x1800060e4  mov     rsp, r11
0x1800060e7  pop     r14
0x1800060e9  pop     rdi
0x1800060ea  pop     rbp
0x1800060eb  retn
```

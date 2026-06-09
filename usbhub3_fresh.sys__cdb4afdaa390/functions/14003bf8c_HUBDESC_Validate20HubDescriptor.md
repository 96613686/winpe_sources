# HUBDESC_Validate20HubDescriptor

- ea: `0x14003bf8c`
- end: `0x14003c39a`
- name: `HUBDESC_Validate20HubDescriptor`
- size: `1038`
- prototype: `char __fastcall(unsigned __int8 *, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140009f30`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x14003bf54`
- `0x14003bf8c`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_Validate20HubDescriptor(unsigned __int8 *a1, __int64 a2, __int64 a3, int a4)
{
  int v4; // r12d
  int v7; // esi
  int v8; // eax
  int v9; // edx
  unsigned int v10; // eax
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned __int16 v13; // ax
  unsigned int v14; // r8d
  unsigned __int8 v15; // dl
  unsigned int i; // r12d
  char v17; // bl
  __int64 v19; // [rsp+28h] [rbp-60h]
  unsigned int v20; // [rsp+40h] [rbp-48h]
  unsigned int v21; // [rsp+90h] [rbp+8h]
  unsigned int v22; // [rsp+98h] [rbp+10h]
  unsigned __int16 v23; // [rsp+98h] [rbp+10h]

  v4 = a4;
  if ( a1 )
  {
    v7 = 0;
    if ( !a1[2] )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(a4, 2, 5, 309, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, 0);
      (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 7);
      v7 = 2;
    }
    v8 = a1[2];
    v9 = 1;
    v21 = (unsigned int)(v8 + 8) >> 3;
    v20 = (unsigned int)(v8 + 7) >> 3;
    v10 = v21 + 7 + v20;
    v11 = *a1;
    v22 = v10;
    if ( v11 < v10 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_dD(v4, v9, 5, 310, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v11, v10);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 1);
      if ( *(_WORD *)a3 > 0x200u || *(_BYTE *)(a3 + 12) )
        v7 = 2;
      v10 = v22;
    }
    v12 = *a1;
    if ( v12 > v10 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_dD(v4, v9, 5, 311, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v12, v10);
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(a3 + 24))(*(_QWORD *)(a3 + 40), 0);
      if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a3) )
        v7 = 2;
    }
    if ( a1[1] != 41 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v19) = a1[1];
        WPP_RECORDER_SF_d(v4, 2, 5, 312, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v19);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 6);
      if ( *(_WORD *)a3 > 0x200u || *(_BYTE *)(a3 + 12) )
        v7 = 2;
    }
    v13 = *(_WORD *)(a1 + 3);
    v23 = v13;
    if ( (v13 & 2) != 0 )
    {
      if ( *(_BYTE *)(a3 + 15) )
        v7 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v19) = *(unsigned __int16 *)(a1 + 3);
        WPP_RECORDER_SF_d(v4, 2, 5, 313, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v19);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 9);
      v13 = v23;
    }
    if ( (v13 & 0xFF00) != 0 )
    {
      if ( *(_BYTE *)(a3 + 15) )
        v7 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v19) = v13;
        WPP_RECORDER_SF_d(v4, 2, 5, 314, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v19);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 9);
    }
    if ( (a1[7] & 1) != 0 )
    {
      if ( *(_BYTE *)(a3 + 15) )
        v7 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(v4, 2, 5, 315, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
      (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 5);
    }
    v14 = v21;
    v15 = -1 << ((a1[2] + 1) & 7);
    if ( v15 != 0xFF && (v15 & a1[v21 + 6]) != 0 )
    {
      if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a3) )
        v7 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(v4, 2, 5, 316, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
      (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 4);
      v14 = v21;
    }
    for ( i = 0; i < v20; ++i )
    {
      if ( a1[i + 7 + v14] != 0xFF )
      {
        if ( HUBDESC_ShouldEnforceWin8ValidationMutable(a3) )
          v7 = 2;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(a4, 2, 5, 317, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
        (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 8);
        v14 = v21;
      }
    }
    if ( !v7 )
      return 1;
    v4 = a4;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(a4, 2, 5, 307, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 2);
  }
  v17 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(v4, 2, 5, 318, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  return v17;
}

```

## disassembly

```asm
0x14003bf8c  mov     rax, rsp
0x14003bf8f  mov     [rax+18h], rbx
0x14003bf93  mov     [rax+20h], r9
0x14003bf97  mov     [rax+10h], edx
0x14003bf9a  push    rbp
0x14003bf9b  push    rsi
0x14003bf9c  push    rdi
0x14003bf9d  push    r12
0x14003bf9f  push    r13
0x14003bfa1  push    r14
0x14003bfa3  push    r15
0x14003bfa5  sub     rsp, 50h
0x14003bfa9  mov     r12, r9
0x14003bfac  mov     rbx, r8
0x14003bfaf  mov     r13, rcx
0x14003bfb2  test    rcx, rcx
0x14003bfb5  jnz     short loc_14003C001
0x14003bfb7  lea     rbp, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003bfbe  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14003bfc5  lea     r15, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003bfcc  lea     edi, [rcx+2]
0x14003bfcf  lea     r14d, [rcx+5]
0x14003bfd3  jz      short loc_14003BFED
0x14003bfd5  mov     r9d, 133h
0x14003bfdb  mov     [rax-68h], r15
0x14003bfdf  mov     r8d, r14d
0x14003bfe2  mov     dl, dil
0x14003bfe5  mov     rcx, r12
0x14003bfe8  call    WPP_RECORDER_SF_
0x14003bfed  mov     rax, [rbx+18h]
0x14003bff1  mov     edx, edi
0x14003bff3  mov     rcx, [rbx+28h]
0x14003bff7  call    _guard_dispatch_icall
0x14003bffc  jmp     loc_14003C35B
0x14003c001  xor     esi, esi
0x14003c003  lea     rbp, WPP_RECORDER_INITIALIZED
0x14003c00a  lea     r15, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003c011  lea     edi, [rsi+2]
0x14003c014  lea     r14d, [rsi+5]
0x14003c018  cmp     [rcx+2], sil
0x14003c01c  jnz     short loc_14003C058
0x14003c01e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003c025  jz      short loc_14003C044
0x14003c027  mov     r9d, 135h
0x14003c02d  mov     dword ptr [rsp+88h+var_60], esi
0x14003c031  mov     r8d, r14d
0x14003c034  mov     [rsp+88h+var_68], r15
0x14003c039  mov     dl, dil
0x14003c03c  mov     rcx, r12
0x14003c03f  call    WPP_RECORDER_SF_d
0x14003c044  mov     rax, [rbx+18h]
0x14003c048  mov     edx, 7
0x14003c04d  mov     rcx, [rbx+28h]
0x14003c051  call    _guard_dispatch_icall
0x14003c056  mov     esi, edi
0x14003c058  movzx   eax, byte ptr [r13+2]
0x14003c05d  mov     edx, 1
0x14003c062  lea     ecx, [rax+8]
0x14003c065  add     eax, 7
0x14003c068  shr     ecx, 3
0x14003c06b  shr     eax, 3
0x14003c06e  mov     [rsp+88h+arg_0], ecx
0x14003c075  add     ecx, 7
0x14003c078  mov     [rsp+88h+var_48], eax
0x14003c07c  add     eax, ecx
0x14003c07e  movzx   ecx, byte ptr [r13+0]
0x14003c083  mov     [rsp+88h+arg_8], eax
0x14003c08a  cmp     ecx, eax
0x14003c08c  jnb     short loc_14003C0E3
0x14003c08e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003c095  jz      short loc_14003C0BD
0x14003c097  mov     [rsp+88h+var_58], eax
0x14003c09b  mov     r9d, 136h
0x14003c0a1  mov     dword ptr [rsp+88h+var_60], ecx
0x14003c0a5  mov     r8d, r14d
0x14003c0a8  mov     rcx, r12
0x14003c0ab  mov     [rsp+88h+var_68], r15
0x14003c0b0  mov     dl, dil
0x14003c0b3  call    WPP_RECORDER_SF_dD
0x14003c0b8  mov     edx, 1
0x14003c0bd  mov     rax, [rbx+18h]
0x14003c0c1  mov     rcx, [rbx+28h]
0x14003c0c5  call    _guard_dispatch_icall
0x14003c0ca  mov     eax, 200h
0x14003c0cf  cmp     [rbx], ax
0x14003c0d2  ja      short loc_14003C0DA
0x14003c0d4  cmp     byte ptr [rbx+0Ch], 0
0x14003c0d8  jz      short loc_14003C0DC
0x14003c0da  mov     esi, edi
0x14003c0dc  mov     eax, [rsp+88h+arg_8]
0x14003c0e3  movzx   ecx, byte ptr [r13+0]
0x14003c0e8  cmp     ecx, eax
0x14003c0ea  jbe     short loc_14003C132
0x14003c0ec  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003c0f3  jz      short loc_14003C116
0x14003c0f5  mov     [rsp+88h+var_58], eax
0x14003c0f9  mov     r9d, 137h
0x14003c0ff  mov     dword ptr [rsp+88h+var_60], ecx
0x14003c103  mov     r8d, r14d
0x14003c106  mov     rcx, r12
0x14003c109  mov     [rsp+88h+var_68], r15
0x14003c10e  mov     dl, dil
0x14003c111  call    WPP_RECORDER_SF_dD
0x14003c116  mov     rax, [rbx+18h]
0x14003c11a  xor     edx, edx
0x14003c11c  mov     rcx, [rbx+28h]
0x14003c120  call    _guard_dispatch_icall
0x14003c125  mov     rcx, rbx
0x14003c128  call    HUBDESC_ShouldEnforceWin8ValidationMutable
0x14003c12d  test    al, al
0x14003c12f  cmovnz  esi, edi
0x14003c132  movzx   eax, byte ptr [r13+1]
0x14003c137  cmp     al, 29h ; ')'
0x14003c139  jz      short loc_14003C185
0x14003c13b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003c142  jz      short loc_14003C161
0x14003c144  mov     dword ptr [rsp+88h+var_60], eax
0x14003c148  mov     r9d, 138h
0x14003c14e  mov     r8d, r14d
0x14003c151  mov     [rsp+88h+var_68], r15
0x14003c156  mov     dl, dil
0x14003c159  mov     rcx, r12
0x14003c15c  call    WPP_RECORDER_SF_d
0x14003c161  mov     rax, [rbx+18h]
0x14003c165  mov     edx, 6
0x14003c16a  mov     rcx, [rbx+28h]
0x14003c16e  call    _guard_dispatch_icall
0x14003c173  mov     eax, 200h
0x14003c178  cmp     [rbx], ax
0x14003c17b  ja      short loc_14003C183
0x14003c17d  cmp     byte ptr [rbx+0Ch], 0
0x14003c181  jz      short loc_14003C185
0x14003c183  mov     esi, edi
0x14003c185  movzx   eax, word ptr [r13+3]
0x14003c18a  mov     word ptr [rsp+88h+arg_8], ax
0x14003c192  test    dil, al
0x14003c195  jz      short loc_14003C1DE
0x14003c197  cmp     byte ptr [rbx+0Fh], 0
0x14003c19b  cmovnz  esi, edi
0x14003c19e  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003c1a5  jz      short loc_14003C1C4
0x14003c1a7  mov     dword ptr [rsp+88h+var_60], eax
0x14003c1ab  mov     r9d, 139h
0x14003c1b1  mov     r8d, r14d
0x14003c1b4  mov     [rsp+88h+var_68], r15
0x14003c1b9  mov     dl, dil
0x14003c1bc  mov     rcx, r12
0x14003c1bf  call    WPP_RECORDER_SF_d
0x14003c1c4  mov     rax, [rbx+18h]
0x14003c1c8  mov     edx, 9
0x14003c1cd  mov     rcx, [rbx+28h]
0x14003c1d1  call    _guard_dispatch_icall
0x14003c1d6  movzx   eax, word ptr [rsp+88h+arg_8]
0x14003c1de  mov     ecx, 0FF00h
0x14003c1e3  test    cx, ax
0x14003c1e6  jz      short loc_14003C22A
0x14003c1e8  cmp     byte ptr [rbx+0Fh], 0
0x14003c1ec  cmovnz  esi, edi
0x14003c1ef  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003c1f6  jz      short loc_14003C218
0x14003c1f8  movzx   eax, ax
0x14003c1fb  mov     r9d, 13Ah
0x14003c201  mov     dword ptr [rsp+88h+var_60], eax
0x14003c205  mov     r8d, r14d
0x14003c208  mov     dl, dil
0x14003c20b  mov     [rsp+88h+var_68], r15
0x14003c210  mov     rcx, r12
0x14003c213  call    WPP_RECORDER_SF_d
0x14003c218  mov     rax, [rbx+18h]
0x14003c21c  mov     edx, 9
0x14003c221  mov     rcx, [rbx+28h]
0x14003c225  call    _guard_dispatch_icall
0x14003c22a  test    byte ptr [r13+7], 1
0x14003c22f  jz      short loc_14003C26A
0x14003c231  cmp     byte ptr [rbx+0Fh], 0
0x14003c235  cmovnz  esi, edi
0x14003c238  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003c23f  jz      short loc_14003C25A
0x14003c241  mov     r9d, 13Bh
0x14003c247  mov     [rsp+88h+var_68], r15
0x14003c24c  mov     r8d, r14d
0x14003c24f  mov     dl, dil
0x14003c252  mov     rcx, r12
0x14003c255  call    WPP_RECORDER_SF_
0x14003c25a  mov     rax, [rbx+18h]
0x14003c25e  mov     edx, r14d
0x14003c261  mov     rcx, [rbx+28h]
0x14003c265  call    _guard_dispatch_icall
0x14003c26a  movzx   ecx, byte ptr [r13+2]
0x14003c26f  mov     edx, 0FFh
0x14003c274  mov     r8d, [rsp+88h+arg_0]
0x14003c27c  inc     ecx
0x14003c27e  and     ecx, 7
0x14003c281  shl     dl, cl
0x14003c283  cmp     dl, 0FFh
0x14003c286  jz      short loc_14003C2DC
0x14003c288  lea     eax, [r8-1]
0x14003c28c  test    [rax+r13+7], dl
0x14003c291  jz      short loc_14003C2DC
0x14003c293  mov     rcx, rbx
0x14003c296  call    HUBDESC_ShouldEnforceWin8ValidationMutable
0x14003c29b  test    al, al
0x14003c29d  cmovnz  esi, edi
0x14003c2a0  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003c2a7  jz      short loc_14003C2C2
0x14003c2a9  mov     r9d, 13Ch
0x14003c2af  mov     [rsp+88h+var_68], r15
0x14003c2b4  mov     r8d, r14d
0x14003c2b7  mov     dl, dil
0x14003c2ba  mov     rcx, r12
0x14003c2bd  call    WPP_RECORDER_SF_
0x14003c2c2  mov     rax, [rbx+18h]
0x14003c2c6  mov     edx, 4
0x14003c2cb  mov     rcx, [rbx+28h]
0x14003c2cf  call    _guard_dispatch_icall
0x14003c2d4  mov     r8d, [rsp+88h+arg_0]
0x14003c2dc  xor     r12d, r12d
0x14003c2df  cmp     [rsp+88h+var_48], r12d
0x14003c2e4  jbe     short loc_14003C34A
0x14003c2e6  lea     eax, [r12+r8]
0x14003c2ea  cmp     byte ptr [rax+r13+7], 0FFh
0x14003c2f0  jz      short loc_14003C340
0x14003c2f2  mov     rcx, rbx
0x14003c2f5  call    HUBDESC_ShouldEnforceWin8ValidationMutable
0x14003c2fa  test    al, al
0x14003c2fc  cmovnz  esi, edi
0x14003c2ff  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003c306  jz      short loc_14003C326
0x14003c308  mov     rcx, [rsp+88h+arg_18]
0x14003c310  mov     r9d, 13Dh
0x14003c316  mov     r8d, r14d
0x14003c319  mov     [rsp+88h+var_68], r15
0x14003c31e  mov     dl, dil
0x14003c321  call    WPP_RECORDER_SF_
0x14003c326  mov     rax, [rbx+18h]
0x14003c32a  mov     edx, 8
0x14003c32f  mov     rcx, [rbx+28h]
0x14003c333  call    _guard_dispatch_icall
0x14003c338  mov     r8d, [rsp+88h+arg_0]
0x14003c340  inc     r12d
0x14003c343  cmp     r12d, [rsp+88h+var_48]
0x14003c348  jb      short loc_14003C2E6
0x14003c34a  test    esi, esi
0x14003c34c  jnz     short loc_14003C353
0x14003c34e  lea     ebx, [rsi+1]
0x14003c351  jmp     short loc_14003C37F
0x14003c353  mov     r12, [rsp+88h+arg_18]
0x14003c35b  xor     bl, bl
0x14003c35d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp; __annotation("TMF:",
0x14003c364  jz      short loc_14003C37F
0x14003c366  mov     r9d, 13Eh
0x14003c36c  mov     [rsp+88h+var_68], r15
0x14003c371  mov     r8d, r14d
0x14003c374  mov     dl, dil
0x14003c377  mov     rcx, r12
0x14003c37a  call    WPP_RECORDER_SF_
0x14003c37f  mov     al, bl
0x14003c381  mov     rbx, [rsp+88h+arg_10]
0x14003c389  add     rsp, 50h
0x14003c38d  pop     r15
0x14003c38f  pop     r14
0x14003c391  pop     r13
0x14003c393  pop     r12
0x14003c395  pop     rdi
0x14003c396  pop     rsi
0x14003c397  pop     rbp
0x14003c398  retn
```

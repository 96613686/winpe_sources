# SsiCredentialsUpdateNotify(_UNICODE_STRING *,_SSI_ATTRIBUTE *,ulong,_SSI_ATTRIBUTE *,_SSI_ATTRIBUTE * *)

- ea: `0x1800277a0`
- end: `0x180027e25`
- name: `?SsiCredentialsUpdateNotify@@YAJPEAU_UNICODE_STRING@@PEAU_SSI_ATTRIBUTE@@K1PEAPEAU2@@Z`
- size: `1669`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _SSI_ATTRIBUTE *, unsigned int, struct _SSI_ATTRIBUTE *, struct _SSI_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x1800061a0`
- `0x180006d00`
- `0x180009770`
- `0x180011fec`
- `0x1800185b8`
- `0x180024ea0`
- `0x1800277a0`
- `0x180029bd0`
- `0x180033564`

## pseudocode

```c
__int64 __fastcall SsiCredentialsUpdateNotify(
        struct _UNICODE_STRING *a1,
        struct _SSI_ATTRIBUTE *a2,
        unsigned int a3,
        struct _SSI_ATTRIBUTE *a4,
        struct _SSI_ATTRIBUTE **a5)
{
  __int64 Memory; // rsi
  PVOID *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // ebx
  __int64 v12; // rax
  int *v13; // rax
  unsigned int v14; // r12d
  __int64 v15; // r15
  __int64 v16; // r9
  __int64 v17; // r11
  __int64 v18; // r14
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  int updated; // eax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  _QWORD *v34; // rcx
  __int64 v35; // rdx
  _DWORD *v36; // rax
  int v38; // [rsp+58h] [rbp-31h]
  _DWORD hMem[3]; // [rsp+5Ch] [rbp-2Dh] BYREF
  UNICODE_STRING Source; // [rsp+68h] [rbp-21h] BYREF
  UNICODE_STRING SourceString; // [rsp+78h] [rbp-11h] BYREF
  __int64 v42[2]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v43[2]; // [rsp+98h] [rbp+Fh] BYREF
  int v44; // [rsp+E8h] [rbp+5Fh]

  v44 = (int)a1;
  Memory = 0;
  memset(hMem, 0, sizeof(hMem));
  *(_OWORD *)v42 = 0;
  Source = 0;
  SourceString = 0;
  *(_OWORD *)v43 = 0;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 1) == 0 )
      goto LABEL_9;
    v10 = 85;
LABEL_8:
    WPP_SF_(v9[2], v10, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
LABEL_9:
    v11 = -1073741811;
    goto LABEL_105;
  }
  if ( !a5 )
  {
    if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 1) == 0 )
      goto LABEL_9;
    v10 = 86;
    goto LABEL_8;
  }
  *a5 = 0;
  if ( a2 && *((_DWORD *)a2 + 4) )
  {
    v12 = *(_QWORD *)a2 - SSIGUID_DIGESTKEY;
    if ( *(_QWORD *)a2 == (_QWORD)SSIGUID_DIGESTKEY )
      v12 = *((_QWORD *)a2 + 1) - *((_QWORD *)&SSIGUID_DIGESTKEY + 1);
    if ( v12 || (v13 = (int *)*((_QWORD *)a2 + 3)) == 0 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_9;
      v10 = 88;
      goto LABEL_8;
    }
    v14 = *v13;
    v15 = *((_QWORD *)v13 + 1);
    if ( *v13 && !v15 )
    {
      v9 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_9;
      v10 = 87;
      goto LABEL_8;
    }
  }
  else
  {
    v14 = 0;
    v15 = 0;
  }
  v16 = SSIGUID_NETBIOSDOMAIN;
  v17 = SSIGUID_DNSDOMAIN;
  v18 = SSIGUID_SAMACCOUNTNAME;
  v38 = 0;
  v19 = 0;
  v20 = SSIGUID_UPN;
  while ( 1 )
  {
    if ( v19 >= a3 )
    {
      updated = CredentialUpdateNotify(
                  v44,
                  v15,
                  v14,
                  0,
                  (__int64)v42,
                  &Source,
                  &SourceString,
                  (__int64)v43,
                  (__int64 *)&hMem[1],
                  hMem);
      v11 = updated;
      if ( updated < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = 98;
          goto LABEL_42;
        }
        goto LABEL_105;
      }
      Memory = DigestAllocateMemory(0x20u);
      if ( Memory )
      {
        v36 = (_DWORD *)DigestAllocateMemory(0x10u);
        *(_QWORD *)(Memory + 24) = v36;
        if ( v36 )
        {
          *(_DWORD *)(Memory + 16) = 1;
          *(_OWORD *)Memory = SSIGUID_DIGESTKEY;
          *v36 = hMem[0];
          *(_QWORD *)(*(_QWORD *)(Memory + 24) + 8LL) = *(_QWORD *)&hMem[1];
          *a5 = (struct _SSI_ATTRIBUTE *)Memory;
          Memory = 0;
          *(_QWORD *)&hMem[1] = 0;
          goto LABEL_105;
        }
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_99:
          v11 = -2146893056;
          goto LABEL_105;
        }
        v35 = 100;
      }
      else
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_99;
        v35 = 99;
      }
      WPP_SF_(v34[2], v35, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
      goto LABEL_99;
    }
    if ( !a4 )
    {
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v33 = 89;
LABEL_88:
        WPP_SF_(v32[2], v33, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
      }
      goto LABEL_89;
    }
    if ( *((_DWORD *)a4 + 4) )
      break;
LABEL_69:
    a4 = (struct _SSI_ATTRIBUTE *)((char *)a4 + 32);
    v38 = ++v19;
  }
  v21 = *(_QWORD *)a4 - v20;
  if ( *(_QWORD *)a4 == v20 )
    v21 = *((_QWORD *)a4 + 1) - 0x142B2F515FAC0F86LL;
  if ( !v21 )
  {
    v22 = *((_QWORD *)a4 + 3);
    if ( *(_DWORD *)v22 && !*(_QWORD *)(v22 + 8) )
    {
      v32 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v33 = 90;
        goto LABEL_88;
      }
      goto LABEL_89;
    }
    UnicodeStringFree(v42);
    updated = UnicodeStringByteDuplicate(v42, *(_QWORD *)(*((_QWORD *)a4 + 3) + 8LL));
    v11 = updated;
    if ( updated < 0 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v25 = 91;
LABEL_42:
        WPP_SF_d(v24[2], v25, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, (unsigned int)updated);
        goto LABEL_105;
      }
      goto LABEL_105;
    }
    goto LABEL_67;
  }
  v26 = *(_QWORD *)a4 - v16;
  if ( *(_QWORD *)a4 == v16 )
    v26 = *((_QWORD *)a4 + 1) - 0x3D035E1A6DAD8290LL;
  if ( v26 )
  {
    v28 = *(_QWORD *)a4 - v17;
    if ( *(_QWORD *)a4 == v17 )
      v28 = *((_QWORD *)a4 + 1) - 0x3BA20E27FD47F6A2LL;
    if ( v28 )
    {
      v30 = *(_QWORD *)a4 - v18;
      if ( *(_QWORD *)a4 == v18 )
        v30 = *((_QWORD *)a4 + 1) - 0x16730836C6E7B8B5LL;
      if ( v30 )
        goto LABEL_68;
      v31 = *((_QWORD *)a4 + 3);
      if ( *(_DWORD *)v31 && !*(_QWORD *)(v31 + 8) )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v33 = 96;
          goto LABEL_88;
        }
        goto LABEL_89;
      }
      UnicodeStringFree(&Source);
      updated = UnicodeStringByteDuplicate(&Source, *(_QWORD *)(*((_QWORD *)a4 + 3) + 8LL));
      v11 = updated;
      if ( updated < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = 97;
          goto LABEL_42;
        }
        goto LABEL_105;
      }
    }
    else
    {
      v29 = *((_QWORD *)a4 + 3);
      if ( *(_DWORD *)v29 && !*(_QWORD *)(v29 + 8) )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v33 = 94;
          goto LABEL_88;
        }
        goto LABEL_89;
      }
      UnicodeStringFree(v43);
      updated = UnicodeStringByteDuplicate(v43, *(_QWORD *)(*((_QWORD *)a4 + 3) + 8LL));
      v11 = updated;
      if ( updated < 0 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = 95;
          goto LABEL_42;
        }
        goto LABEL_105;
      }
    }
LABEL_67:
    v18 = SSIGUID_SAMACCOUNTNAME;
    v17 = SSIGUID_DNSDOMAIN;
    v16 = SSIGUID_NETBIOSDOMAIN;
    v20 = SSIGUID_UPN;
LABEL_68:
    v19 = v38;
    goto LABEL_69;
  }
  v27 = *((_QWORD *)a4 + 3);
  if ( *(_DWORD *)v27 && !*(_QWORD *)(v27 + 8) )
  {
    v32 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v33 = 92;
      goto LABEL_88;
    }
LABEL_89:
    v11 = -1073741811;
    goto LABEL_105;
  }
  UnicodeStringFree(&SourceString);
  updated = UnicodeStringByteDuplicate(&SourceString, *(_QWORD *)(*((_QWORD *)a4 + 3) + 8LL));
  v11 = updated;
  if ( updated >= 0 )
    goto LABEL_67;
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v25 = 93;
    goto LABEL_42;
  }
LABEL_105:
  if ( *(_QWORD *)&hMem[1] )
  {
    DigestFreeMemory(*(HLOCAL *)&hMem[1]);
    *(_QWORD *)&hMem[1] = 0;
  }
  if ( Memory )
    SsiCredentialsUpdateFree((HLOCAL)Memory);
  UnicodeStringFree(&Source);
  UnicodeStringFree(&SourceString);
  UnicodeStringFree(v42);
  UnicodeStringFree(v43);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x1800277a0  mov     rax, rsp
0x1800277a3  mov     [rax+10h], rbx
0x1800277a7  mov     [rax+18h], r8d
0x1800277ab  mov     [rax+8], rcx
0x1800277af  push    rbp
0x1800277b0  push    rsi
0x1800277b1  push    rdi
0x1800277b2  push    r12
0x1800277b4  push    r13
0x1800277b6  push    r14
0x1800277b8  push    r15
0x1800277ba  lea     rbp, [rax-57h]
0x1800277be  sub     rsp, 0A0h
0x1800277c5  xorps   xmm0, xmm0
0x1800277c8  xorps   xmm1, xmm1
0x1800277cb  mov     rbx, rdx
0x1800277ce  mov     rdi, r9
0x1800277d1  xor     edx, edx
0x1800277d3  mov     r14, rcx
0x1800277d6  mov     qword ptr [rbp+4Fh+hMem+4], rdx
0x1800277da  mov     esi, edx
0x1800277dc  mov     dword ptr [rbp+4Fh+hMem], edx
0x1800277df  movups  xmmword ptr [rbp+4Fh+var_50], xmm0
0x1800277e3  movups  xmmword ptr [rbp+4Fh+var_70.Length], xmm1
0x1800277e7  movups  xmmword ptr [rbp+4Fh+var_60.Length], xmm0
0x1800277eb  movups  xmmword ptr [rbp+4Fh+var_40], xmm1
0x1800277ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277f6  lea     r8, WPP_GLOBAL_Control
0x1800277fd  lea     r9, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180027804  cmp     rcx, r8
0x180027807  jz      short loc_180027835
0x180027809  test    byte ptr [rcx+1Ch], 80h
0x18002780d  jz      short loc_180027835
0x18002780f  mov     rcx, [rcx+10h]
0x180027813  lea     edx, [rsi+54h]
0x180027816  mov     r8, r9
0x180027819  call    WPP_SF_
0x18002781e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027825  lea     r8, WPP_GLOBAL_Control
0x18002782c  xor     edx, edx
0x18002782e  lea     r9, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180027835  test    r14, r14
0x180027838  jnz     short loc_18002785F
0x18002783a  cmp     rcx, r8
0x18002783d  jz      short loc_180027855
0x18002783f  test    byte ptr [rcx+1Ch], 1
0x180027843  jz      short loc_180027855
0x180027845  lea     edx, [r14+55h]
0x180027849  mov     rcx, [rcx+10h]
0x18002784d  mov     r8, r9
0x180027850  call    WPP_SF_
0x180027855  mov     ebx, 0C000000Dh
0x18002785a  jmp     loc_180027D90
0x18002785f  mov     r13, [rbp+4Fh+arg_20]
0x180027863  test    r13, r13
0x180027866  jnz     short loc_180027879
0x180027868  cmp     rcx, r8
0x18002786b  jz      short loc_180027855
0x18002786d  test    byte ptr [rcx+1Ch], 1
0x180027871  jz      short loc_180027855
0x180027873  lea     edx, [r13+56h]
0x180027877  jmp     short loc_180027849
0x180027879  mov     [r13+0], rdx
0x18002787d  test    rbx, rbx
0x180027880  jz      short loc_1800278FC
0x180027882  cmp     [rbx+10h], edx
0x180027885  jz      short loc_1800278FC
0x180027887  mov     rax, [rbx]
0x18002788a  sub     rax, qword ptr cs:SSIGUID_DIGESTKEY
0x180027891  jnz     short loc_18002789E
0x180027893  mov     rax, [rbx+8]
0x180027897  sub     rax, qword ptr cs:SSIGUID_DIGESTKEY+8
0x18002789e  test    rax, rax
0x1800278a1  jnz     short loc_1800278D8
0x1800278a3  mov     rax, [rbx+18h]
0x1800278a7  test    rax, rax
0x1800278aa  jz      short loc_1800278D8
0x1800278ac  mov     r12d, [rax]
0x1800278af  mov     r15, [rax+8]
0x1800278b3  test    r12d, r12d
0x1800278b6  jz      short loc_180027902
0x1800278b8  test    r15, r15
0x1800278bb  jnz     short loc_180027902
0x1800278bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800278c4  cmp     rcx, r8
0x1800278c7  jz      short loc_180027855
0x1800278c9  test    byte ptr [rcx+1Ch], 1
0x1800278cd  jz      short loc_180027855
0x1800278cf  lea     edx, [r15+57h]
0x1800278d3  jmp     loc_180027849
0x1800278d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800278df  cmp     rcx, r8
0x1800278e2  jz      loc_180027855
0x1800278e8  test    byte ptr [rcx+1Ch], 1
0x1800278ec  jz      loc_180027855
0x1800278f2  mov     edx, 58h ; 'X'
0x1800278f7  jmp     loc_180027849
0x1800278fc  mov     r12d, edx
0x1800278ff  mov     r15, rdx
0x180027902  mov     rcx, cs:qword_18003C6B0
0x180027909  mov     r8, cs:qword_18003C690
0x180027910  mov     r9, cs:SSIGUID_NETBIOSDOMAIN
0x180027917  mov     r10, cs:qword_18003C760
0x18002791e  mov     r11, cs:SSIGUID_DNSDOMAIN
0x180027925  mov     rbx, cs:qword_18003C750
0x18002792c  mov     r14, cs:SSIGUID_SAMACCOUNTNAME
0x180027933  mov     [rbp+4Fh+var_80], edx
0x180027936  mov     eax, [rbp+4Fh+var_80]
0x180027939  mov     rdx, cs:SSIGUID_UPN
0x180027940  cmp     eax, [rbp+4Fh+arg_10]
0x180027943  jnb     loc_180027C6D
0x180027949  test    rdi, rdi
0x18002794c  jz      loc_180027C35
0x180027952  cmp     [rdi+10h], esi
0x180027955  jz      loc_180027B5E
0x18002795b  mov     rax, [rdi]
0x18002795e  sub     rax, rdx
0x180027961  jnz     short loc_18002796A
0x180027963  mov     rax, [rdi+8]
0x180027967  sub     rax, rcx
0x18002796a  test    rax, rax
0x18002796d  jnz     short loc_1800279E7
0x18002796f  mov     rax, [rdi+18h]
0x180027973  cmp     [rax], esi
0x180027975  jz      short loc_180027981
0x180027977  cmp     [rax+8], rsi
0x18002797b  jz      loc_180027B6C
0x180027981  lea     rcx, [rbp+4Fh+var_50]
0x180027985  call    UnicodeStringFree
0x18002798a  mov     rdx, [rdi+18h]
0x18002798e  lea     rcx, [rbp+4Fh+var_50]
0x180027992  movzx   r8d, word ptr [rdx]
0x180027996  mov     rdx, [rdx+8]
0x18002799a  call    UnicodeStringByteDuplicate
0x18002799f  mov     ebx, eax
0x1800279a1  test    eax, eax
0x1800279a3  jns     loc_180027B23
0x1800279a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279b0  lea     rdi, WPP_GLOBAL_Control
0x1800279b7  cmp     rcx, rdi
0x1800279ba  jz      loc_180027D97
0x1800279c0  test    byte ptr [rcx+1Ch], 1
0x1800279c4  jz      loc_180027D97
0x1800279ca  mov     edx, 5Bh ; '['
0x1800279cf  mov     rcx, [rcx+10h]
0x1800279d3  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x1800279da  mov     r9d, eax
0x1800279dd  call    WPP_SF_d
0x1800279e2  jmp     loc_180027D97
0x1800279e7  mov     rax, [rdi]
0x1800279ea  sub     rax, r9
0x1800279ed  jnz     short loc_1800279F6
0x1800279ef  mov     rax, [rdi+8]
0x1800279f3  sub     rax, r8
0x1800279f6  test    rax, rax
0x1800279f9  jnz     short loc_180027A60
0x1800279fb  mov     rax, [rdi+18h]
0x1800279ff  cmp     [rax], esi
0x180027a01  jz      short loc_180027A0D
0x180027a03  cmp     [rax+8], rsi
0x180027a07  jz      loc_180027B97
0x180027a0d  lea     rcx, [rbp+4Fh+var_60]
0x180027a11  call    UnicodeStringFree
0x180027a16  mov     rdx, [rdi+18h]
0x180027a1a  lea     rcx, [rbp+4Fh+var_60]
0x180027a1e  movzx   r8d, word ptr [rdx]
0x180027a22  mov     rdx, [rdx+8]
0x180027a26  call    UnicodeStringByteDuplicate
0x180027a2b  mov     ebx, eax
0x180027a2d  test    eax, eax
0x180027a2f  jns     loc_180027B23
0x180027a35  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a3c  lea     rdi, WPP_GLOBAL_Control
0x180027a43  cmp     rcx, rdi
0x180027a46  jz      loc_180027D97
0x180027a4c  test    byte ptr [rcx+1Ch], 1
0x180027a50  jz      loc_180027D97
0x180027a56  mov     edx, 5Dh ; ']'
0x180027a5b  jmp     loc_1800279CF
0x180027a60  mov     rax, [rdi]
0x180027a63  sub     rax, r11
0x180027a66  jnz     short loc_180027A6F
0x180027a68  mov     rax, [rdi+8]
0x180027a6c  sub     rax, r10
0x180027a6f  test    rax, rax
0x180027a72  jnz     short loc_180027AD5
0x180027a74  mov     rax, [rdi+18h]
0x180027a78  cmp     [rax], esi
0x180027a7a  jz      short loc_180027A86
0x180027a7c  cmp     [rax+8], rsi
0x180027a80  jz      loc_180027BC2
0x180027a86  lea     rcx, [rbp+4Fh+var_40]
0x180027a8a  call    UnicodeStringFree
0x180027a8f  mov     rdx, [rdi+18h]
0x180027a93  lea     rcx, [rbp+4Fh+var_40]
0x180027a97  movzx   r8d, word ptr [rdx]
0x180027a9b  mov     rdx, [rdx+8]
0x180027a9f  call    UnicodeStringByteDuplicate
0x180027aa4  mov     ebx, eax
0x180027aa6  test    eax, eax
0x180027aa8  jns     short loc_180027B23
0x180027aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ab1  lea     rdi, WPP_GLOBAL_Control
0x180027ab8  cmp     rcx, rdi
0x180027abb  jz      loc_180027D97
0x180027ac1  test    byte ptr [rcx+1Ch], 1
0x180027ac5  jz      loc_180027D97
0x180027acb  mov     edx, 5Fh ; '_'
0x180027ad0  jmp     loc_1800279CF
0x180027ad5  mov     rax, [rdi]
0x180027ad8  sub     rax, r14
0x180027adb  jnz     short loc_180027AE4
0x180027add  mov     rax, [rdi+8]
0x180027ae1  sub     rax, rbx
0x180027ae4  test    rax, rax
0x180027ae7  jnz     short loc_180027B5B
0x180027ae9  mov     rax, [rdi+18h]
0x180027aed  cmp     [rax], esi
0x180027aef  jz      short loc_180027AFB
0x180027af1  cmp     [rax+8], rsi
0x180027af5  jz      loc_180027BEA
0x180027afb  lea     rcx, [rbp+4Fh+var_70]
0x180027aff  call    UnicodeStringFree
0x180027b04  mov     rdx, [rdi+18h]
0x180027b08  lea     rcx, [rbp+4Fh+var_70]
0x180027b0c  movzx   r8d, word ptr [rdx]
0x180027b10  mov     rdx, [rdx+8]
0x180027b14  call    UnicodeStringByteDuplicate
0x180027b19  mov     ebx, eax
0x180027b1b  test    eax, eax
0x180027b1d  js      loc_180027C0A
0x180027b23  mov     r14, cs:SSIGUID_SAMACCOUNTNAME
0x180027b2a  mov     rbx, cs:qword_18003C750
0x180027b31  mov     r11, cs:SSIGUID_DNSDOMAIN
0x180027b38  mov     r10, cs:qword_18003C760
0x180027b3f  mov     r9, cs:SSIGUID_NETBIOSDOMAIN
0x180027b46  mov     r8, cs:qword_18003C690
0x180027b4d  mov     rdx, cs:SSIGUID_UPN
0x180027b54  mov     rcx, cs:qword_18003C6B0
0x180027b5b  mov     eax, [rbp+4Fh+var_80]
0x180027b5e  add     rdi, 20h ; ' '
0x180027b62  inc     eax
0x180027b64  mov     [rbp+4Fh+var_80], eax
0x180027b67  jmp     loc_180027940
0x180027b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b73  lea     rdi, WPP_GLOBAL_Control
0x180027b7a  cmp     rcx, rdi
0x180027b7d  jz      loc_180027C63
0x180027b83  test    byte ptr [rcx+1Ch], 1
0x180027b87  jz      loc_180027C63
0x180027b8d  mov     edx, 5Ah ; 'Z'
0x180027b92  jmp     loc_180027C53
0x180027b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b9e  lea     rdi, WPP_GLOBAL_Control
0x180027ba5  cmp     rcx, rdi
0x180027ba8  jz      loc_180027C63
0x180027bae  test    byte ptr [rcx+1Ch], 1
0x180027bb2  jz      loc_180027C63
0x180027bb8  mov     edx, 5Ch ; '\'
0x180027bbd  jmp     loc_180027C53
0x180027bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180027bc9  lea     rdi, WPP_GLOBAL_Control
0x180027bd0  cmp     rcx, rdi
0x180027bd3  jz      loc_180027C63
0x180027bd9  test    byte ptr [rcx+1Ch], 1
0x180027bdd  jz      loc_180027C63
0x180027be3  mov     edx, 5Eh ; '^'
0x180027be8  jmp     short loc_180027C53
0x180027bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180027bf1  lea     rdi, WPP_GLOBAL_Control
0x180027bf8  cmp     rcx, rdi
0x180027bfb  jz      short loc_180027C63
0x180027bfd  test    byte ptr [rcx+1Ch], 1
0x180027c01  jz      short loc_180027C63
0x180027c03  mov     edx, 60h ; '`'
0x180027c08  jmp     short loc_180027C53
0x180027c0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c11  lea     rdi, WPP_GLOBAL_Control
0x180027c18  cmp     rcx, rdi
0x180027c1b  jz      loc_180027D97
0x180027c21  test    byte ptr [rcx+1Ch], 1
0x180027c25  jz      loc_180027D97
0x180027c2b  mov     edx, 61h ; 'a'
0x180027c30  jmp     loc_1800279CF
0x180027c35  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c3c  lea     rdi, WPP_GLOBAL_Control
0x180027c43  cmp     rcx, rdi
0x180027c46  jz      short loc_180027C63
0x180027c48  test    byte ptr [rcx+1Ch], 1
0x180027c4c  jz      short loc_180027C63
0x180027c4e  mov     edx, 59h ; 'Y'
0x180027c53  mov     rcx, [rcx+10h]
0x180027c57  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180027c5e  call    WPP_SF_
0x180027c63  mov     ebx, 0C000000Dh
0x180027c68  jmp     loc_180027D97
0x180027c6d  mov     rcx, qword ptr [rbp+4Fh+arg_0]; int
0x180027c71  lea     rax, [rbp+4Fh+hMem]
0x180027c75  mov     [rsp+48h], rax; __int64
0x180027c7a  xor     r9d, r9d; int
  ... truncated ...
```

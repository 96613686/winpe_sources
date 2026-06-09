# UbpmpQueueActionInstance

- ea: `0x180003890`
- end: `0x180003d29`
- name: `UbpmpQueueActionInstance`
- size: `1177`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008030`
- `0x18000a198`
- `0x18002c480`
- `0x18002e764`

## callees

- `0x180003890`
- `0x180003d30`
- `0x180004e10`
- `0x18000f9a0`
- `0x180019d90`
- `0x18001cd78`
- `0x18001e9f4`
- `0x180032dd8`
- `0x180032e38`
- `0x180035804`
- `0x180036100`
- `0x18003618c`
- `0x18003d7d2`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003b03`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180003b03`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180003bc4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180003bc4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180003af0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180003af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c6c`
- `RPCRT4!UuidEqual` at `0x180003959`
- `RPCRT4!UuidEqual` at `0x180003959`

## pseudocode

```c
DWORD __fastcall UbpmpQueueActionInstance(int a1, _QWORD *a2, int a3)
{
  void *v4; // rcx
  __int64 *v6; // rbx
  DWORD LengthSid; // ebp
  void *v8; // rcx
  DWORD result; // eax
  const unsigned __int16 ***v10; // rax
  const unsigned __int16 ***v11; // rbx
  DWORD v12; // eax
  __int64 v13; // rax
  const unsigned __int16 ****v14; // rcx
  int v15; // r8d
  void *v16; // rdx
  _QWORD *v17; // rcx
  char LastError; // al
  __int64 v19; // rdx
  const unsigned __int16 **v20; // rax
  RPC_STATUS Status; // [rsp+68h] [rbp+10h] BYREF

  v4 = (void *)a2[5];
  v6 = *(__int64 **)(*a2 + 256LL);
  if ( v4 )
    LengthSid = GetLengthSid(v4);
  else
    LengthSid = 0;
  Status = 0;
  while ( v6 != (__int64 *)(*a2 + 256LL) )
  {
    if ( !a1 )
    {
      result = UuidEqual((UUID *)((char *)v6 + 20), (UUID *)a2[6], &Status);
      if ( result )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          return WPP_SF_iS(
                   *((_QWORD *)WPP_GLOBAL_Control + 2),
                   *(_QWORD *)(*a2 + 24LL),
                   a3,
                   a2[8],
                   *(_QWORD *)(*(_QWORD *)(*a2 + 24LL) + 8LL));
        return result;
      }
    }
    if ( *((_DWORD *)v6 + 4) == a1 && *((_DWORD *)v6 + 12) == *((_DWORD *)a2 + 9) )
    {
      v8 = (void *)v6[7];
      if ( v8 )
      {
        v16 = (void *)a2[5];
        if ( !v16 || !EqualSid(v8, v16) )
          goto LABEL_7;
      }
      else if ( a2[5] )
      {
        goto LABEL_7;
      }
      result = a1 - 2;
      if ( (unsigned int)(a1 - 2) <= 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          return WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, a3, a1, *(_QWORD *)(*(_QWORD *)(*a2 + 24LL) + 8LL));
        return result;
      }
    }
LABEL_7:
    v6 = (__int64 *)*v6;
  }
  v10 = (const unsigned __int16 ***)UbpmAlloc(LengthSid + 144);
  v11 = v10;
  if ( v10 )
  {
    v12 = UbpmUtilsCloneStringArray(*((_BYTE *)a2 + 88), (const unsigned __int16 **)a2[12], v10 + 14);
    if ( v12 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 88;
        goto LABEL_55;
      }
    }
    else
    {
      v12 = UbpmUtilsCloneStringArray(*((_BYTE *)a2 + 108), (const unsigned __int16 **)a2[14], v11 + 16);
      if ( v12 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 89;
          goto LABEL_55;
        }
      }
      else
      {
        if ( a2[5] )
        {
          v11[7] = (const unsigned __int16 **)(v11 + 18);
          if ( !CopySid(LengthSid, v11 + 18, (PSID)a2[5]) )
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                90,
                (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
                *(_QWORD *)(*(_QWORD *)(*a2 + 24LL) + 8LL),
                LastError);
            goto LABEL_37;
          }
        }
        *((_DWORD *)v11 + 4) = a1;
        *((_DWORD *)v11 + 22) = *((_DWORD *)a2 + 26);
        if ( !a2[3] )
        {
LABEL_24:
          _InterlockedIncrement64((volatile signed __int64 *)(*a2 + 64LL));
          *(_OWORD *)((char *)v11 + 20) = *(_OWORD *)a2[6];
          v11[5] = (const unsigned __int16 **)a2[8];
          *((_DWORD *)v11 + 12) = *((_DWORD *)a2 + 9);
          v11[8] = (const unsigned __int16 **)a2[1];
          *((_DWORD *)v11 + 18) = *((_DWORD *)a2 + 18);
          v11[10] = (const unsigned __int16 **)a2[10];
          *((_BYTE *)v11 + 104) = *((_BYTE *)a2 + 88);
          *((_BYTE *)v11 + 124) = *((_BYTE *)a2 + 108);
          *((_DWORD *)v11 + 30) = *((_DWORD *)a2 + 14);
          v11[17] = (const unsigned __int16 **)*a2;
          v13 = *a2 + 256LL;
          v14 = *(const unsigned __int16 *****)(*a2 + 264LL);
          if ( *v14 != (const unsigned __int16 ***)v13 )
            __fastfail(3u);
          *v11 = (const unsigned __int16 **)v13;
          v11[1] = (const unsigned __int16 **)v14;
          *v14 = v11;
          *(_QWORD *)(v13 + 8) = v11;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              92,
              WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
              *(_QWORD *)(*(_QWORD *)(*a2 + 24LL) + 8LL));
          result = UbpmTriggerConsumerPublishStateChange(*a2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            return WPP_SF_iSddi(
                     *((_QWORD *)WPP_GLOBAL_Control + 2),
                     *(_QWORD *)(*a2 + 24LL),
                     v15,
                     a2[8],
                     *(_QWORD *)(*(_QWORD *)(*a2 + 24LL) + 8LL),
                     *((_DWORD *)a2 + 9),
                     *((_DWORD *)a2 + 18),
                     a2[10]);
          return result;
        }
        v20 = (const unsigned __int16 **)UbpmAlloc(*((unsigned int *)a2 + 8));
        v11[12] = v20;
        if ( v20 )
        {
          memcpy_0(v20, (const void *)a2[3], *((unsigned int *)a2 + 8));
          *((_DWORD *)v11 + 23) = *((_DWORD *)a2 + 8);
          goto LABEL_24;
        }
        v12 = GetLastError();
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 91;
LABEL_55:
          WPP_SF_d(v17[2], v19, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids, v12);
        }
      }
    }
LABEL_37:
    UBPM_MIDL_user_free(v11[14]);
    UBPM_MIDL_user_free(v11[16]);
    UBPM_MIDL_user_free(v11[12]);
    return UBPM_MIDL_user_free(v11);
  }
  result = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return WPP_SF_iSd(
             *((_QWORD *)WPP_GLOBAL_Control + 2),
             87,
             (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
             a2[8],
             *(_QWORD *)(*(_QWORD *)(*a2 + 24LL) + 8LL),
             result);
  return result;
}

```

## disassembly

```asm
0x180003890  mov     [rsp+arg_10], rbx
0x180003895  push    rbp
0x180003896  push    rsi
0x180003897  push    rdi
0x180003898  sub     rsp, 40h
0x18000389c  mov     rbx, [rdx]
0x18000389f  mov     esi, ecx
0x1800038a1  mov     rcx, [rdx+28h]; pSid
0x1800038a5  mov     rdi, rdx
0x1800038a8  mov     rbx, [rbx+100h]
0x1800038af  test    rcx, rcx
0x1800038b2  jnz     loc_180003B03
0x1800038b8  xor     ebp, ebp
0x1800038ba  mov     [rsp+58h+Status], 0
0x1800038c2  mov     rax, [rdi]
0x1800038c5  add     rax, 100h
0x1800038cb  cmp     rbx, rax
0x1800038ce  jz      loc_1800039AA
0x1800038d4  test    esi, esi
0x1800038d6  jz      short loc_18000394C
0x1800038d8  cmp     [rbx+10h], esi
0x1800038db  jz      short loc_1800038E2
0x1800038dd  mov     rbx, [rbx]
0x1800038e0  jmp     short loc_1800038C2
0x1800038e2  mov     eax, [rdi+24h]
0x1800038e5  cmp     [rbx+30h], eax
0x1800038e8  jnz     short loc_1800038DD
0x1800038ea  mov     rcx, [rbx+38h]; pSid1
0x1800038ee  test    rcx, rcx
0x1800038f1  jnz     loc_180003AE3
0x1800038f7  cmp     [rdi+28h], rcx
0x1800038fb  jnz     short loc_1800038DD
0x1800038fd  lea     eax, [rsi-2]
0x180003900  cmp     eax, 1
0x180003903  ja      short loc_1800038DD
0x180003905  mov     rcx, cs:WPP_GLOBAL_Control
0x18000390c  lea     rbp, WPP_GLOBAL_Control
0x180003913  cmp     rcx, rbp
0x180003916  jz      loc_180003AD6
0x18000391c  test    byte ptr [rcx+1Ch], 1
0x180003920  jz      loc_180003AD6
0x180003926  mov     rax, [rdi]
0x180003929  mov     edx, 56h ; 'V'
0x18000392e  mov     rcx, [rcx+10h]
0x180003932  mov     r9d, esi
0x180003935  mov     rax, [rax+18h]
0x180003939  mov     rax, [rax+8]
0x18000393d  mov     [rsp+58h+var_38], rax
0x180003942  call    WPP_SF_dS
0x180003947  jmp     loc_180003AD6
0x18000394c  mov     rdx, [rdi+30h]; Uuid2
0x180003950  lea     rcx, [rbx+14h]; Uuid1
0x180003954  lea     r8, [rsp+58h+Status]; Status
0x180003959  call    cs:__imp_UuidEqual
0x18000395f  test    eax, eax
0x180003961  jz      loc_1800038D8
0x180003967  mov     rcx, cs:WPP_GLOBAL_Control
0x18000396e  lea     rbp, WPP_GLOBAL_Control
0x180003975  cmp     rcx, rbp
0x180003978  jz      loc_180003AD6
0x18000397e  test    byte ptr [rcx+1Ch], 1
0x180003982  jz      loc_180003AD6
0x180003988  mov     rax, [rdi]
0x18000398b  mov     r9, [rdi+40h]
0x18000398f  mov     rcx, [rcx+10h]
0x180003993  mov     rdx, [rax+18h]
0x180003997  mov     rax, [rdx+8]
0x18000399b  mov     [rsp+58h+var_38], rax
0x1800039a0  call    WPP_SF_iS
0x1800039a5  jmp     loc_180003AD6
0x1800039aa  lea     ecx, [rbp+90h]; Size
0x1800039b0  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x1800039b5  mov     rbx, rax
0x1800039b8  test    rax, rax
0x1800039bb  jz      loc_180003B4F
0x1800039c1  mov     rdx, [rdi+60h]; unsigned __int16 **
0x1800039c5  lea     r8, [rax+70h]; unsigned __int16 ***
0x1800039c9  movzx   ecx, byte ptr [rdi+58h]; unsigned __int8
0x1800039cd  mov     [rsp+58h+arg_0], r14
0x1800039d2  call    ?UbpmUtilsCloneStringArray@@YAKEPEAPEBGPEAPEAPEBG@Z; UbpmUtilsCloneStringArray(uchar,ushort const * *,ushort const * * *)
0x1800039d7  test    eax, eax
0x1800039d9  jnz     loc_180003C22
0x1800039df  mov     rdx, [rdi+70h]; unsigned __int16 **
0x1800039e3  lea     r8, [rbx+80h]; unsigned __int16 ***
0x1800039ea  movzx   ecx, byte ptr [rdi+6Ch]; unsigned __int8
0x1800039ee  call    ?UbpmUtilsCloneStringArray@@YAKEPEAPEBGPEAPEAPEBG@Z; UbpmUtilsCloneStringArray(uchar,ushort const * *,ushort const * * *)
0x1800039f3  test    eax, eax
0x1800039f5  jnz     loc_180003B10
0x1800039fb  cmp     qword ptr [rdi+28h], 0
0x180003a00  jnz     loc_180003BB3
0x180003a06  mov     [rbx+10h], esi
0x180003a09  mov     eax, [rdi+68h]
0x180003a0c  mov     [rbx+58h], eax
0x180003a0f  cmp     qword ptr [rdi+18h], 0
0x180003a14  jnz     loc_180003C5B
0x180003a1a  mov     rax, [rdi]
0x180003a1d  lock inc qword ptr [rax+40h]
0x180003a22  mov     rax, [rdi+30h]
0x180003a26  movups  xmm0, xmmword ptr [rax]
0x180003a29  movups  xmmword ptr [rbx+14h], xmm0
0x180003a2d  mov     rax, [rdi+40h]
0x180003a31  mov     [rbx+28h], rax
0x180003a35  mov     eax, [rdi+24h]
0x180003a38  mov     [rbx+30h], eax
0x180003a3b  mov     rax, [rdi+8]
0x180003a3f  mov     [rbx+40h], rax
0x180003a43  mov     eax, [rdi+48h]
0x180003a46  mov     [rbx+48h], eax
0x180003a49  mov     rax, [rdi+50h]
0x180003a4d  mov     [rbx+50h], rax
0x180003a51  movzx   eax, byte ptr [rdi+58h]
0x180003a55  mov     [rbx+68h], al
0x180003a58  movzx   eax, byte ptr [rdi+6Ch]
0x180003a5c  mov     [rbx+7Ch], al
0x180003a5f  mov     eax, [rdi+38h]
0x180003a62  mov     [rbx+78h], eax
0x180003a65  mov     rax, [rdi]
0x180003a68  mov     [rbx+88h], rax
0x180003a6f  mov     rax, [rdi]
0x180003a72  add     rax, 100h
0x180003a78  mov     rcx, [rax+8]
0x180003a7c  cmp     [rcx], rax
0x180003a7f  jnz     loc_180003BAC
0x180003a85  mov     [rbx], rax
0x180003a88  mov     [rbx+8], rcx
0x180003a8c  mov     [rcx], rbx
0x180003a8f  mov     [rax+8], rbx
0x180003a93  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a9a  lea     rbp, WPP_GLOBAL_Control
0x180003aa1  cmp     rcx, rbp
0x180003aa4  jz      short loc_180003AB0
0x180003aa6  test    byte ptr [rcx+1Ch], 20h
0x180003aaa  jnz     loc_180003CCB
0x180003ab0  mov     rcx, [rdi]
0x180003ab3  call    UbpmTriggerConsumerPublishStateChange
0x180003ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003abf  cmp     rcx, rbp
0x180003ac2  jz      short loc_180003AD1
0x180003ac4  test    dword ptr [rcx+1Ch], 200h
0x180003acb  jnz     loc_180003CF0
0x180003ad1  mov     r14, [rsp+58h+arg_0]
0x180003ad6  mov     rbx, [rsp+58h+arg_10]
0x180003adb  add     rsp, 40h
0x180003adf  pop     rdi
0x180003ae0  pop     rsi
0x180003ae1  pop     rbp
0x180003ae2  retn
0x180003ae3  mov     rdx, [rdi+28h]; pSid2
0x180003ae7  test    rdx, rdx
0x180003aea  jz      loc_1800038DD
0x180003af0  call    cs:__imp_EqualSid
0x180003af6  test    eax, eax
0x180003af8  jnz     loc_1800038FD
0x180003afe  jmp     loc_1800038DD
0x180003b03  call    cs:__imp_GetLengthSid
0x180003b09  mov     ebp, eax
0x180003b0b  jmp     loc_1800038BA
0x180003b10  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b17  lea     rbp, WPP_GLOBAL_Control
0x180003b1e  cmp     rcx, rbp
0x180003b21  jnz     loc_180003C4A
0x180003b27  mov     rcx, [rbx+70h]
0x180003b2b  call    UBPM_MIDL_user_free
0x180003b30  mov     rcx, [rbx+80h]
0x180003b37  call    UBPM_MIDL_user_free
0x180003b3c  mov     rcx, [rbx+60h]
0x180003b40  call    UBPM_MIDL_user_free
0x180003b45  mov     rcx, rbx
0x180003b48  call    UBPM_MIDL_user_free
0x180003b4d  jmp     short loc_180003AD1
0x180003b4f  call    cs:__imp_GetLastError
0x180003b55  mov     r8d, eax
0x180003b58  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b5f  lea     rbp, WPP_GLOBAL_Control
0x180003b66  cmp     rcx, rbp
0x180003b69  jz      loc_180003AD6
0x180003b6f  test    byte ptr [rcx+1Ch], 1
0x180003b73  jz      loc_180003AD6
0x180003b79  mov     rdx, [rdi]
0x180003b7c  mov     r9, [rdi+40h]
0x180003b80  mov     rcx, [rcx+10h]
0x180003b84  mov     [rsp+58h+var_30], r8d
0x180003b89  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180003b90  mov     rax, [rdx+18h]
0x180003b94  mov     edx, 57h ; 'W'
0x180003b99  mov     rax, [rax+8]
0x180003b9d  mov     [rsp+58h+var_38], rax
0x180003ba2  call    WPP_SF_iSd
0x180003ba7  jmp     loc_180003AD6
0x180003bac  mov     ecx, 3
0x180003bb1  int     29h; Win8: RtlFailFast(ecx)
0x180003bb3  lea     rdx, [rbx+90h]; pDestinationSid
0x180003bba  mov     ecx, ebp; nDestinationSidLength
0x180003bbc  mov     [rbx+38h], rdx
0x180003bc0  mov     r8, [rdi+28h]; pSourceSid
0x180003bc4  call    cs:__imp_CopySid
0x180003bca  test    eax, eax
0x180003bcc  jnz     loc_180003A06
0x180003bd2  call    cs:__imp_GetLastError
0x180003bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bdf  lea     rbp, WPP_GLOBAL_Control
0x180003be6  cmp     rcx, rbp
0x180003be9  jz      loc_180003B27
0x180003bef  test    byte ptr [rcx+1Ch], 1
0x180003bf3  jz      loc_180003B27
0x180003bf9  mov     rdx, [rdi]
0x180003bfc  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180003c03  mov     rcx, [rcx+10h]
0x180003c07  mov     dword ptr [rsp+58h+var_38], eax
0x180003c0b  mov     r9, [rdx+18h]
0x180003c0f  mov     edx, 5Ah ; 'Z'
0x180003c14  mov     r9, [r9+8]
0x180003c18  call    WPP_SF_Sd
0x180003c1d  jmp     loc_180003B27
0x180003c22  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c29  lea     rbp, WPP_GLOBAL_Control
0x180003c30  cmp     rcx, rbp
0x180003c33  jz      loc_180003B27
0x180003c39  test    byte ptr [rcx+1Ch], 1
0x180003c3d  jz      loc_180003B27
0x180003c43  mov     edx, 58h ; 'X'
0x180003c48  jmp     short loc_180003C98
0x180003c4a  test    byte ptr [rcx+1Ch], 1
0x180003c4e  jz      loc_180003B27
0x180003c54  mov     edx, 59h ; 'Y'
0x180003c59  jmp     short loc_180003C98
0x180003c5b  mov     ecx, [rdi+20h]; Size
0x180003c5e  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180003c63  mov     [rbx+60h], rax
0x180003c67  test    rax, rax
0x180003c6a  jnz     short loc_180003CB0
0x180003c6c  call    cs:__imp_GetLastError
0x180003c72  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c79  lea     rbp, WPP_GLOBAL_Control
0x180003c80  cmp     rcx, rbp
0x180003c83  jz      loc_180003B27
0x180003c89  test    byte ptr [rcx+1Ch], 1
0x180003c8d  jz      loc_180003B27
0x180003c93  mov     edx, 5Bh ; '['
0x180003c98  mov     rcx, [rcx+10h]
0x180003c9c  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180003ca3  mov     r9d, eax
0x180003ca6  call    WPP_SF_d
0x180003cab  jmp     loc_180003B27
0x180003cb0  mov     r8d, [rdi+20h]; Size
0x180003cb4  mov     rcx, rax; void *
0x180003cb7  mov     rdx, [rdi+18h]; Src
0x180003cbb  call    memcpy_0
0x180003cc0  mov     eax, [rdi+20h]
0x180003cc3  mov     [rbx+5Ch], eax
0x180003cc6  jmp     loc_180003A1A
0x180003ccb  mov     rax, [rdi]
0x180003cce  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x180003cd5  mov     rcx, [rcx+10h]
0x180003cd9  mov     edx, 5Ch ; '\'
0x180003cde  mov     r9, [rax+18h]
0x180003ce2  mov     r9, [r9+8]
0x180003ce6  call    WPP_SF_S
0x180003ceb  jmp     loc_180003AB0
0x180003cf0  mov     rax, [rdi]
0x180003cf3  mov     r9, [rdi+40h]
0x180003cf7  mov     rcx, [rcx+10h]
0x180003cfb  mov     rdx, [rax+18h]
0x180003cff  mov     rax, [rdi+50h]
0x180003d03  mov     [rsp+58h+var_20], rax
0x180003d08  mov     eax, [rdi+48h]
0x180003d0b  mov     [rsp+58h+var_28], eax
0x180003d0f  mov     eax, [rdi+24h]
0x180003d12  mov     [rsp+58h+var_30], eax
0x180003d16  mov     rax, [rdx+8]
0x180003d1a  mov     [rsp+58h+var_38], rax
0x180003d1f  call    WPP_SF_iSddi
0x180003d24  jmp     loc_180003AD1
```

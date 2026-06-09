# HUBDESC_InternalValidateInterfaceDescriptor

- ea: `0x140038894`
- end: `0x140038e1b`
- name: `HUBDESC_InternalValidateInterfaceDescriptor`
- size: `1415`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14003cce8`

## callees

- `0x1400024b8`
- `0x1400025a4`
- `0x1400067ac`
- `0x14001cf04`
- `0x14002d940`
- `0x140038894`
- `0x140038fac`
- `0x140045570`

## import_xrefs

- `ntoskrnl!RtlSetBit` at `0x140038c85`
- `ntoskrnl!RtlSetBit` at `0x140038dba`
- `ntoskrnl!RtlSetBit` at `0x140038c85`
- `ntoskrnl!RtlSetBit` at `0x140038dba`
- `ntoskrnl!RtlClearAllBits` at `0x140038c70`
- `ntoskrnl!RtlClearAllBits` at `0x140038d88`
- `ntoskrnl!RtlClearAllBits` at `0x140038c70`
- `ntoskrnl!RtlClearAllBits` at `0x140038d88`

## pseudocode

```c
char __fastcall HUBDESC_InternalValidateInterfaceDescriptor(
        char *a1,
        __int64 a2,
        unsigned int *a3,
        int *a4,
        __int64 a5)
{
  int *v5; // rdi
  unsigned int v9; // eax
  int v10; // ebp
  char v11; // r12
  int v12; // r13d
  __int64 *v13; // r8
  unsigned int v14; // ebp
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // ecx
  unsigned __int64 v18; // rbp
  unsigned __int64 v19; // r12
  int v20; // r15d
  bool v21; // r14
  int v22; // r8d
  int v23; // edx
  char v24; // r15
  unsigned __int8 v25; // al
  int v27; // [rsp+50h] [rbp-58h] BYREF

  v27 = 0;
  v5 = a4;
  if ( a4 )
  {
    if ( *(_BYTE *)(a2 + 48) )
      *a4 = 0;
  }
  else
  {
    v5 = &v27;
  }
  v9 = (unsigned __int8)*a1;
  v10 = *(_DWORD *)(a2 + 72);
  v11 = 1;
  *a3 = v9;
  v12 = (_DWORD)a1 - *(_DWORD *)(a2 + 56);
  v13 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
  v14 = v10 - v12;
  v15 = 9;
  if ( (unsigned __int8)v9 >= 9u )
    goto LABEL_19;
  (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(
    *(_QWORD *)(a2 + 40),
    99,
    WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  v15 = 9;
  if ( v14 < 9 )
  {
    v17 = *a3;
  }
  else
  {
    *a3 = 9;
    v17 = 9;
  }
  if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
    *v5 = 2;
  if ( v17 >= 9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_DDDD(a5, v15, 5, 117, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a1, v12, 9, v17);
      v15 = 9;
    }
    v13 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
LABEL_19:
    if ( (unsigned __int8)*a1 > 9u )
    {
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_DDD(
          a5,
          v15,
          (unsigned int)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          118,
          (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
          *a1,
          v12,
          9);
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(*(_QWORD *)(a2 + 40), 98, v13);
    }
    if ( *a3 <= v14 )
    {
      v18 = (unsigned __int8)a1[2];
      v19 = (unsigned __int8)a1[3];
      v20 = *(_DWORD *)(a2 + 256) & 1;
      v21 = !v20 || (_BYTE)v18 != *(_BYTE *)(a2 + 80);
      HUBDESC_InternalValidateLastInterface(a2, v5, a5);
      if ( *v5 != 1 )
      {
        v23 = 0;
        if ( v21 )
        {
          v24 = v20 ^ 1;
          if ( _bittest64(*(const signed __int64 **)(a2 + 216), v18) )
          {
            if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
              *v5 = 2;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v23) = 2;
              WPP_RECORDER_SF_dD(a5, v23, 5, 120, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v12, v18);
            }
            (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 103);
            v23 = 0;
          }
          if ( !v24 && *(_BYTE *)(a2 + 80) > (unsigned __int8)v18 )
          {
            if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
              *v5 = 2;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v23) = 2;
              WPP_RECORDER_SF_DDD(
                a5,
                v23,
                v22,
                121,
                (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                v12,
                v18,
                *(_BYTE *)(a2 + 80));
            }
            (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 106);
            v23 = 0;
          }
          if ( (_BYTE)v19 )
          {
            if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
              *v5 = 2;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v23) = 2;
              WPP_RECORDER_SF_DDD(
                a5,
                v23,
                v22,
                122,
                (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                v12,
                v18,
                v19);
            }
            (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 104);
          }
          RtlClearAllBits((PRTL_BITMAP)(a2 + 88));
          RtlSetBit((PRTL_BITMAP)(a2 + 208), v18);
          *(_BYTE *)(a2 + 80) = v18;
          ++*(_WORD *)(a2 + 202);
        }
        else
        {
          if ( _bittest64(*(const signed __int64 **)(a2 + 96), v19) )
          {
            if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
              *v5 = 2;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v23) = 2;
              WPP_RECORDER_SF_DDD(
                a5,
                v23,
                v22,
                123,
                (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                v19,
                v12,
                v18);
            }
            (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 101);
            v23 = 0;
          }
          if ( *(_BYTE *)(a2 + 81) >= (unsigned __int8)v19 )
          {
            if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
              *v5 = 2;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v23) = 2;
              WPP_RECORDER_SF_DDD(
                a5,
                v23,
                v22,
                124,
                (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
                v12,
                v19,
                *(_BYTE *)(a2 + 81));
            }
            (*(void (__fastcall **)(_QWORD, __int64))(a2 + 24))(*(_QWORD *)(a2 + 40), 105);
          }
        }
        RtlClearAllBits((PRTL_BITMAP)(a2 + 136));
        *(_BYTE *)(a2 + 185) = 0;
        v25 = a1[4];
        *(_DWORD *)(a2 + 256) &= ~2u;
        *(_BYTE *)(a2 + 184) = v25;
        RtlSetBit((PRTL_BITMAP)(a2 + 88), v19);
        *(_BYTE *)(a2 + 81) = v19;
      }
      v11 = 1;
    }
    else
    {
      if ( *(_WORD *)a2 > 0x200u || *(_BYTE *)(a2 + 12) || *(_BYTE *)(a2 + 13) )
        *v5 = 2;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 2;
        WPP_RECORDER_SF_d(a5, v15, 5, 119, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v12);
      }
      (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(a2 + 24))(*(_QWORD *)(a2 + 40), 100, v13);
    }
LABEL_85:
    if ( !*v5 )
      return v11;
    goto LABEL_86;
  }
  *v5 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_DDD(a5, v15, v16, 116, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *a1, v12, 9);
    goto LABEL_85;
  }
LABEL_86:
  v11 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_(a5, v15, 5, 125, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v11;
}

```

## disassembly

```asm
0x140038894  mov     [rsp+arg_0], rcx
0x140038899  push    rbx
0x14003889a  push    rbp
0x14003889b  push    rsi
0x14003889c  push    rdi
0x14003889d  push    r12
0x14003889f  push    r13
0x1400388a1  push    r14
0x1400388a3  push    r15
0x1400388a5  sub     rsp, 68h
0x1400388a9  mov     [rsp+0A8h+var_58], 0
0x1400388b1  mov     rdi, r9
0x1400388b4  mov     r14, r8
0x1400388b7  mov     rbx, rdx
0x1400388ba  mov     r15, rcx
0x1400388bd  test    r9, r9
0x1400388c0  jnz     short loc_1400388C9
0x1400388c2  lea     rdi, [rsp+0A8h+var_58]
0x1400388c7  jmp     short loc_1400388D6
0x1400388c9  cmp     byte ptr [rdx+30h], 0
0x1400388cd  jz      short loc_1400388D6
0x1400388cf  mov     dword ptr [r9], 0
0x1400388d6  movzx   eax, byte ptr [rcx]
0x1400388d9  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400388e0  mov     ebp, [rdx+48h]
0x1400388e3  mov     r12d, 1
0x1400388e9  mov     r13d, r15d
0x1400388ec  mov     [r8], eax
0x1400388ef  sub     r13d, [rdx+38h]
0x1400388f3  lea     r8, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400388fa  sub     ebp, r13d
0x1400388fd  mov     ecx, 200h
0x140038902  lea     edx, [r12+8]
0x140038907  cmp     al, dl
0x140038909  jnb     loc_1400389FA
0x14003890f  mov     rax, [rbx+18h]
0x140038913  lea     edx, [r12+62h]
0x140038918  mov     rcx, [rbx+28h]
0x14003891c  call    _guard_dispatch_icall
0x140038921  lea     edx, [r12+8]
0x140038926  cmp     ebp, edx
0x140038928  jb      short loc_140038931
0x14003892a  mov     [r14], edx
0x14003892d  mov     ecx, edx
0x14003892f  jmp     short loc_140038934
0x140038931  mov     ecx, [r14]
0x140038934  mov     eax, 200h
0x140038939  cmp     [rbx], ax
0x14003893c  ja      short loc_14003894A
0x14003893e  cmp     byte ptr [rbx+0Ch], 0
0x140038942  jnz     short loc_14003894A
0x140038944  cmp     byte ptr [rbx+0Dh], 0
0x140038948  jz      short loc_140038950
0x14003894a  mov     dword ptr [rdi], 2
0x140038950  cmp     ecx, edx
0x140038952  jnb     short loc_1400389A2
0x140038954  mov     [rdi], r12d
0x140038957  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003895e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140038965  jz      loc_140038DD5
0x14003896b  movzx   eax, byte ptr [r15]
0x14003896f  mov     r9d, 74h ; 't'
0x140038975  mov     rcx, [rsp+0A8h+arg_20]
0x14003897d  mov     [rsp+0A8h+var_70], edx
0x140038981  mov     dl, 2
0x140038983  mov     [rsp+0A8h+var_78], r13d
0x140038988  mov     [rsp+0A8h+var_80], eax
0x14003898c  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038993  mov     [rsp+0A8h+var_88], rax
0x140038998  call    WPP_RECORDER_SF_DDD
0x14003899d  jmp     loc_140038DD0
0x1400389a2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400389a9  jz      short loc_1400389F1
0x1400389ab  movzx   eax, byte ptr [r15]
0x1400389af  mov     r9d, 75h ; 'u'
0x1400389b5  mov     [rsp+0A8h+var_68], ecx
0x1400389b9  mov     rcx, [rsp+0A8h+arg_20]
0x1400389c1  mov     [rsp+0A8h+var_70], edx
0x1400389c5  mov     dl, 2
0x1400389c7  mov     [rsp+0A8h+var_78], r13d
0x1400389cc  lea     r8d, [r9-70h]
0x1400389d0  mov     [rsp+0A8h+var_80], eax
0x1400389d4  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400389db  mov     [rsp+0A8h+var_88], rax
0x1400389e0  call    WPP_RECORDER_SF_DDDD
0x1400389e5  mov     edx, 9
0x1400389ea  mov     ecx, 200h
0x1400389ef  jmp     short loc_1400389F3
0x1400389f1  mov     ecx, eax
0x1400389f3  lea     r8, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x1400389fa  cmp     [r15], dl
0x1400389fd  jbe     short loc_140038A5C
0x1400389ff  cmp     [rbx], cx
0x140038a02  ja      short loc_140038A10
0x140038a04  cmp     byte ptr [rbx+0Ch], 0
0x140038a08  jnz     short loc_140038A10
0x140038a0a  cmp     byte ptr [rbx+0Dh], 0
0x140038a0e  jz      short loc_140038A16
0x140038a10  mov     dword ptr [rdi], 2
0x140038a16  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140038a1d  jz      short loc_140038A4A
0x140038a1f  movzx   eax, byte ptr [r15]
0x140038a23  mov     r9d, 76h ; 'v'
0x140038a29  mov     rcx, [rsp+0A8h+arg_20]
0x140038a31  mov     [rsp+0A8h+var_70], edx
0x140038a35  mov     dl, 2
0x140038a37  mov     [rsp+0A8h+var_78], r13d
0x140038a3c  mov     [rsp+0A8h+var_80], eax
0x140038a40  mov     [rsp+0A8h+var_88], r8
0x140038a45  call    WPP_RECORDER_SF_DDD
0x140038a4a  mov     rax, [rbx+18h]
0x140038a4e  mov     edx, 62h ; 'b'
0x140038a53  mov     rcx, [rbx+28h]
0x140038a57  call    _guard_dispatch_icall
0x140038a5c  cmp     [r14], ebp
0x140038a5f  jbe     short loc_140038AC7
0x140038a61  mov     eax, 200h
0x140038a66  cmp     [rbx], ax
0x140038a69  ja      short loc_140038A77
0x140038a6b  cmp     byte ptr [rbx+0Ch], 0
0x140038a6f  jnz     short loc_140038A77
0x140038a71  cmp     byte ptr [rbx+0Dh], 0
0x140038a75  jz      short loc_140038A7D
0x140038a77  mov     dword ptr [rdi], 2
0x140038a7d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140038a84  jz      short loc_140038AB0
0x140038a86  mov     rcx, [rsp+0A8h+arg_20]
0x140038a8e  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038a95  mov     r9d, 77h ; 'w'
0x140038a9b  mov     [rsp+0A8h+var_80], r13d
0x140038aa0  mov     dl, 2
0x140038aa2  mov     [rsp+0A8h+var_88], rax
0x140038aa7  lea     r8d, [r9-72h]
0x140038aab  call    WPP_RECORDER_SF_d
0x140038ab0  mov     rax, [rbx+18h]
0x140038ab4  mov     edx, 64h ; 'd'
0x140038ab9  mov     rcx, [rbx+28h]
0x140038abd  call    _guard_dispatch_icall
0x140038ac2  jmp     loc_140038DD0
0x140038ac7  movzx   ebp, byte ptr [r15+2]
0x140038acc  mov     eax, 1
0x140038ad1  movzx   r12d, byte ptr [r15+3]
0x140038ad6  mov     r15d, [rbx+100h]
0x140038add  and     r15d, eax
0x140038ae0  jz      short loc_140038AED
0x140038ae2  cmp     bpl, [rbx+50h]
0x140038ae6  jnz     short loc_140038AED
0x140038ae8  xor     r14b, r14b
0x140038aeb  jmp     short loc_140038AF0
0x140038aed  mov     r14b, al
0x140038af0  mov     r8, [rsp+0A8h+arg_20]
0x140038af8  mov     rdx, rdi
0x140038afb  mov     rcx, rbx
0x140038afe  call    HUBDESC_InternalValidateLastInterface
0x140038b03  mov     eax, 1
0x140038b08  cmp     [rdi], eax
0x140038b0a  jz      loc_140038DCA
0x140038b10  xor     edx, edx
0x140038b12  test    r14b, r14b
0x140038b15  mov     r14d, 200h
0x140038b1b  jz      loc_140038CA6
0x140038b21  xor     r15b, al
0x140038b24  mov     rax, [rbx+0D8h]
0x140038b2b  bt      [rax], rbp
0x140038b2f  setb    al
0x140038b32  test    al, al
0x140038b34  jz      short loc_140038B97
0x140038b36  cmp     [rbx], r14w
0x140038b3a  ja      short loc_140038B46
0x140038b3c  cmp     [rbx+0Ch], dl
0x140038b3f  jnz     short loc_140038B46
0x140038b41  cmp     [rbx+0Dh], dl
0x140038b44  jz      short loc_140038B4C
0x140038b46  mov     dword ptr [rdi], 2
0x140038b4c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140038b53  jz      short loc_140038B83
0x140038b55  mov     rcx, [rsp+0A8h+arg_20]
0x140038b5d  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038b64  mov     r9d, 78h ; 'x'
0x140038b6a  mov     [rsp+0A8h+var_78], ebp
0x140038b6e  mov     [rsp+0A8h+var_80], r13d
0x140038b73  mov     dl, 2
0x140038b75  mov     [rsp+0A8h+var_88], rax
0x140038b7a  lea     r8d, [r9-73h]
0x140038b7e  call    WPP_RECORDER_SF_dD
0x140038b83  mov     rax, [rbx+18h]
0x140038b87  mov     edx, 67h ; 'g'
0x140038b8c  mov     rcx, [rbx+28h]
0x140038b90  call    _guard_dispatch_icall
0x140038b95  xor     edx, edx
0x140038b97  test    r15b, r15b
0x140038b9a  jnz     short loc_140038C07
0x140038b9c  cmp     [rbx+50h], bpl
0x140038ba0  jbe     short loc_140038C07
0x140038ba2  cmp     [rbx], r14w
0x140038ba6  ja      short loc_140038BB2
0x140038ba8  cmp     [rbx+0Ch], dl
0x140038bab  jnz     short loc_140038BB2
0x140038bad  cmp     [rbx+0Dh], dl
0x140038bb0  jz      short loc_140038BB8
0x140038bb2  mov     dword ptr [rdi], 2
0x140038bb8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140038bbf  jz      short loc_140038BF3
0x140038bc1  movzx   eax, byte ptr [rbx+50h]
0x140038bc5  mov     r9d, 79h ; 'y'
0x140038bcb  mov     rcx, [rsp+0A8h+arg_20]
0x140038bd3  mov     dl, 2
0x140038bd5  mov     [rsp+0A8h+var_70], eax
0x140038bd9  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038be0  mov     [rsp+0A8h+var_78], ebp
0x140038be4  mov     [rsp+0A8h+var_80], r13d
0x140038be9  mov     [rsp+0A8h+var_88], rax
0x140038bee  call    WPP_RECORDER_SF_DDD
0x140038bf3  mov     rax, [rbx+18h]
0x140038bf7  mov     edx, 6Ah ; 'j'
0x140038bfc  mov     rcx, [rbx+28h]
0x140038c00  call    _guard_dispatch_icall
0x140038c05  xor     edx, edx
0x140038c07  test    r12b, r12b
0x140038c0a  jz      short loc_140038C6C
0x140038c0c  cmp     [rbx], r14w
0x140038c10  ja      short loc_140038C1C
0x140038c12  cmp     [rbx+0Ch], dl
0x140038c15  jnz     short loc_140038C1C
0x140038c17  cmp     [rbx+0Dh], dl
0x140038c1a  jz      short loc_140038C22
0x140038c1c  mov     dword ptr [rdi], 2
0x140038c22  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140038c29  jz      short loc_140038C5A
0x140038c2b  mov     rcx, [rsp+0A8h+arg_20]
0x140038c33  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038c3a  mov     [rsp+0A8h+var_70], r12d
0x140038c3f  mov     r9d, 7Ah ; 'z'
0x140038c45  mov     [rsp+0A8h+var_78], ebp
0x140038c49  mov     dl, 2
0x140038c4b  mov     [rsp+0A8h+var_80], r13d
0x140038c50  mov     [rsp+0A8h+var_88], rax
0x140038c55  call    WPP_RECORDER_SF_DDD
0x140038c5a  mov     rax, [rbx+18h]
0x140038c5e  mov     edx, 68h ; 'h'
0x140038c63  mov     rcx, [rbx+28h]
0x140038c67  call    _guard_dispatch_icall
0x140038c6c  lea     rcx, [rbx+58h]; BitMapHeader
0x140038c70  call    cs:__imp_RtlClearAllBits
0x140038c77  nop     dword ptr [rax+rax+00h]
0x140038c7c  mov     edx, ebp; BitNumber
0x140038c7e  lea     rcx, [rbx+0D0h]; BitMapHeader
0x140038c85  call    cs:__imp_RtlSetBit
0x140038c8c  nop     dword ptr [rax+rax+00h]
0x140038c91  mov     eax, 1
0x140038c96  mov     [rbx+50h], bpl
0x140038c9a  add     [rbx+0CAh], ax
0x140038ca1  jmp     loc_140038D81
0x140038ca6  mov     rax, [rbx+60h]
0x140038caa  bt      [rax], r12
0x140038cae  setb    al
0x140038cb1  test    al, al
0x140038cb3  jz      short loc_140038D17
0x140038cb5  cmp     [rbx], r14w
0x140038cb9  ja      short loc_140038CC5
0x140038cbb  cmp     [rbx+0Ch], dl
0x140038cbe  jnz     short loc_140038CC5
0x140038cc0  cmp     [rbx+0Dh], dl
0x140038cc3  jz      short loc_140038CCB
0x140038cc5  mov     dword ptr [rdi], 2
0x140038ccb  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140038cd2  jz      short loc_140038D03
0x140038cd4  mov     rcx, [rsp+0A8h+arg_20]
0x140038cdc  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038ce3  mov     [rsp+0A8h+var_70], ebp
0x140038ce7  mov     r9d, 7Bh ; '{'
0x140038ced  mov     [rsp+0A8h+var_78], r13d
0x140038cf2  mov     dl, 2
0x140038cf4  mov     [rsp+0A8h+var_80], r12d
0x140038cf9  mov     [rsp+0A8h+var_88], rax
0x140038cfe  call    WPP_RECORDER_SF_DDD
0x140038d03  mov     rax, [rbx+18h]
0x140038d07  mov     edx, 65h ; 'e'
0x140038d0c  mov     rcx, [rbx+28h]
0x140038d10  call    _guard_dispatch_icall
0x140038d15  xor     edx, edx
0x140038d17  cmp     [rbx+51h], r12b
0x140038d1b  jb      short loc_140038D81
0x140038d1d  cmp     [rbx], r14w
0x140038d21  ja      short loc_140038D2D
0x140038d23  cmp     [rbx+0Ch], dl
0x140038d26  jnz     short loc_140038D2D
0x140038d28  cmp     [rbx+0Dh], dl
0x140038d2b  jz      short loc_140038D33
0x140038d2d  mov     dword ptr [rdi], 2
0x140038d33  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140038d3a  jz      short loc_140038D6F
0x140038d3c  movzx   eax, byte ptr [rbx+51h]
0x140038d40  mov     r9d, 7Ch ; '|'
0x140038d46  mov     rcx, [rsp+0A8h+arg_20]
0x140038d4e  mov     dl, 2
0x140038d50  mov     [rsp+0A8h+var_70], eax
0x140038d54  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x140038d5b  mov     [rsp+0A8h+var_78], r12d
0x140038d60  mov     [rsp+0A8h+var_80], r13d
  ... truncated ...
```

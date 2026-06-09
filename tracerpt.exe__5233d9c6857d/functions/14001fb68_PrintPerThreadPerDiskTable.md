# PrintPerThreadPerDiskTable

- ea: `0x14001fb68`
- end: `0x14001fd73`
- name: `PrintPerThreadPerDiskTable`
- size: `523`
- prototype: `__int64 __fastcall(struct _iobuf *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001f330`

## callees

- `0x1400164c4`
- `0x14001fb68`

## string_xrefs

- `0x14001fcc3`: `	<Item>\n		<Data name='image'>%s</Data>\n		<Data name='pid'>%d</Data>\n		<Data name='authority'>%s</Data>\n		<Data name='ioRate' visible='false'>%1.3f</Data>\n		<Data name='readRate'>%1.3f</Data>\n		<Data name='readSize'>%d</Data>\n		<Data name='writeRate'>%1.3f</Data>\n		<Data name='writeSize'>%d</Data>\n	</Item>\n`

## pseudocode

```c
void __fastcall PrintPerThreadPerDiskTable(struct _iobuf *a1, int a2)
{
  unsigned __int64 v3; // rbp
  LPVOID *v5; // rsi
  int v6; // r9d
  LPVOID *v7; // r8
  struct _PROCESS_RECORD *v8; // rdi
  int v9; // r10d
  struct _PROCESS_RECORD *i; // rcx
  __int64 *v11; // rax
  int v12; // r15d
  __int64 *j; // rbx
  unsigned int v14; // r8d
  int v15; // ecx
  int v16; // r9d
  double v17; // xmm0_8
  double v18; // xmm2_8
  unsigned int v19; // eax
  const unsigned __int16 *v20; // r8
  double v21; // xmm1_8
  const unsigned __int16 *v22; // rcx
  __int64 v23; // [rsp+38h] [rbp-60h]
  __int64 v24; // [rsp+48h] [rbp-50h]

  v3 = *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&CurrentSystem;
  if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&CurrentSystem >= 0x989680u )
  {
    v5 = (LPVOID *)qword_140082140;
    v6 = 0;
    v7 = (LPVOID *)qword_140082140;
    if ( qword_140082140 != &qword_140082140 )
    {
      v8 = qword_140082130;
      while ( !v6 )
      {
        v9 = *((_DWORD *)v7 + 4);
        for ( i = qword_140082130; i != (struct _PROCESS_RECORD *)&qword_140082130; i = *(struct _PROCESS_RECORD **)i )
        {
          v11 = (__int64 *)*((_QWORD *)i + 6);
          if ( v11 != (__int64 *)((char *)i + 48) && !v6 )
          {
            while ( v9 != *((_DWORD *)v11 + 4) || v9 != a2 )
            {
              v11 = (__int64 *)*v11;
              if ( v11 == (__int64 *)((char *)i + 48) )
                goto LABEL_13;
            }
            v6 = 1;
          }
LABEL_13:
          ;
        }
        v7 = (LPVOID *)*v7;
        if ( v7 == &qword_140082140 )
        {
          if ( !v6 )
            return;
          goto LABEL_16;
        }
      }
      do
      {
LABEL_16:
        v12 = *((_DWORD *)v5 + 4);
        if ( v8 != (struct _PROCESS_RECORD *)&qword_140082130 )
        {
          do
          {
            for ( j = (__int64 *)*((_QWORD *)v8 + 6); j != (__int64 *)((char *)v8 + 48); j = (__int64 *)*j )
            {
              if ( v12 == a2 && v12 == *((_DWORD *)j + 4) )
              {
                v14 = *((_DWORD *)j + 8) + *((_DWORD *)j + 12);
                v15 = *((_DWORD *)j + 9);
                if ( v15 )
                  v16 = *((_DWORD *)j + 11) / (unsigned int)v15;
                else
                  v16 = 0;
                v17 = (double)(int)(v3 / 0x989680);
                v18 = (double)v15 / v17;
                if ( v14 )
                  v19 = (*((_DWORD *)j + 10) + *((_DWORD *)j + 13)) / v14;
                else
                  v19 = 0;
                LODWORD(v24) = v16;
                v20 = L"-";
                LODWORD(v23) = v19;
                v22 = L"-";
                if ( *((_QWORD *)v8 + 12) )
                  v22 = (const unsigned __int16 *)*((_QWORD *)v8 + 12);
                if ( *((_QWORD *)v8 + 13) )
                  v20 = (const unsigned __int16 *)*((_QWORD *)v8 + 13);
                v21 = (double)(*((_DWORD *)j + 8) + *((_DWORD *)j + 12));
                TracerptFWPrintf(
                  a1,
                  (wchar_t *)L"\t<Item>\r\n"
                              "\t\t<Data name='image'>%s</Data>\r\n"
                              "\t\t<Data name='pid'>%d</Data>\r\n"
                              "\t\t<Data name='authority'>%s</Data>\r\n"
                              "\t\t<Data name='ioRate' visible='false'>%1.3f</Data>\r\n"
                              "\t\t<Data name='readRate'>%1.3f</Data>\r\n"
                              "\t\t<Data name='readSize'>%d</Data>\r\n"
                              "\t\t<Data name='writeRate'>%1.3f</Data>\r\n"
                              "\t\t<Data name='writeSize'>%d</Data>\r\n"
                              "\t</Item>\r\n",
                  v20,
                  *((unsigned int *)v8 + 30),
                  v22,
                  v21 / v17 + v18,
                  v21 / v17,
                  v23,
                  v18,
                  v24);
              }
            }
            v8 = *(struct _PROCESS_RECORD **)v8;
          }
          while ( v8 != (struct _PROCESS_RECORD *)&qword_140082130 );
          v8 = qword_140082130;
        }
        v5 = (LPVOID *)*v5;
      }
      while ( v5 != &qword_140082140 );
    }
  }
}

```

## disassembly

```asm
0x14001fb68  push    rbx
0x14001fb6a  push    rbp
0x14001fb6b  push    rsi
0x14001fb6c  push    rdi
0x14001fb6d  push    r12
0x14001fb6f  push    r13
0x14001fb71  push    r14
0x14001fb73  push    r15
0x14001fb75  sub     rsp, 58h
0x14001fb79  mov     rbp, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x14001fb80  mov     r12d, edx
0x14001fb83  sub     rbp, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x14001fb8a  mov     r13, rcx
0x14001fb8d  cmp     rbp, 989680h
0x14001fb94  jb      loc_14001FD62
0x14001fb9a  mov     rsi, cs:qword_140082140
0x14001fba1  lea     rbx, qword_140082140
0x14001fba8  xor     r9d, r9d
0x14001fbab  mov     r8, rsi
0x14001fbae  cmp     rsi, rbx
0x14001fbb1  jz      loc_14001FD62
0x14001fbb7  mov     rdi, cs:qword_140082130
0x14001fbbe  lea     r11, qword_140082130
0x14001fbc5  test    r9d, r9d
0x14001fbc8  jnz     short loc_14001FC1B
0x14001fbca  mov     r10d, [r8+10h]
0x14001fbce  mov     rcx, rdi
0x14001fbd1  cmp     rdi, r11
0x14001fbd4  jz      short loc_14001FC0A
0x14001fbd6  lea     rdx, [rcx+30h]
0x14001fbda  mov     rax, [rdx]
0x14001fbdd  cmp     rax, rdx
0x14001fbe0  jz      short loc_14001FC02
0x14001fbe2  test    r9d, r9d
0x14001fbe5  jnz     short loc_14001FC02
0x14001fbe7  cmp     r10d, [rax+10h]
0x14001fbeb  jnz     short loc_14001FBF2
0x14001fbed  cmp     r10d, r12d
0x14001fbf0  jz      short loc_14001FBFC
0x14001fbf2  mov     rax, [rax]
0x14001fbf5  cmp     rax, rdx
0x14001fbf8  jnz     short loc_14001FBE7
0x14001fbfa  jmp     short loc_14001FC02
0x14001fbfc  mov     r9d, 1
0x14001fc02  mov     rcx, [rcx]
0x14001fc05  cmp     rcx, r11
0x14001fc08  jnz     short loc_14001FBD6
0x14001fc0a  mov     r8, [r8]
0x14001fc0d  cmp     r8, rbx
0x14001fc10  jnz     short loc_14001FBC5
0x14001fc12  test    r9d, r9d
0x14001fc15  jz      loc_14001FD62
0x14001fc1b  mov     r15d, [rsi+10h]
0x14001fc1f  cmp     rdi, r11
0x14001fc22  jz      loc_14001FD56
0x14001fc28  lea     r14, [rdi+30h]
0x14001fc2c  mov     rbx, [r14]
0x14001fc2f  cmp     rbx, r14
0x14001fc32  jz      loc_14001FD3C
0x14001fc38  cmp     r15d, r12d
0x14001fc3b  jnz     loc_14001FD29
0x14001fc41  cmp     r15d, [rbx+10h]
0x14001fc45  jnz     loc_14001FD29
0x14001fc4b  mov     r8d, [rbx+30h]
0x14001fc4f  add     r8d, [rbx+20h]
0x14001fc53  mov     ecx, [rbx+24h]
0x14001fc56  test    ecx, ecx
0x14001fc58  jnz     short loc_14001FC5F
0x14001fc5a  xor     r9d, r9d
0x14001fc5d  jmp     short loc_14001FC69
0x14001fc5f  mov     eax, [rbx+2Ch]
0x14001fc62  xor     edx, edx
0x14001fc64  div     ecx
0x14001fc66  mov     r9d, eax
0x14001fc69  mov     rax, 0D6BF94D5E57A42BDh
0x14001fc73  xorps   xmm0, xmm0
0x14001fc76  mul     rbp
0x14001fc79  shr     rdx, 17h
0x14001fc7d  test    rdx, rdx
0x14001fc80  js      short loc_14001FC89
0x14001fc82  cvtsi2sd xmm0, rdx
0x14001fc87  jmp     short loc_14001FC9E
0x14001fc89  mov     rax, rdx
0x14001fc8c  and     edx, 1
0x14001fc8f  shr     rax, 1
0x14001fc92  or      rax, rdx
0x14001fc95  cvtsi2sd xmm0, rax
0x14001fc9a  addsd   xmm0, xmm0
0x14001fc9e  xorps   xmm2, xmm2
0x14001fca1  cvtsi2sd xmm2, rcx
0x14001fca6  divsd   xmm2, xmm0
0x14001fcaa  test    r8d, r8d
0x14001fcad  jnz     short loc_14001FCB3
0x14001fcaf  xor     eax, eax
0x14001fcb1  jmp     short loc_14001FCBE
0x14001fcb3  mov     eax, [rbx+34h]
0x14001fcb6  xor     edx, edx
0x14001fcb8  add     eax, [rbx+28h]
0x14001fcbb  div     r8d
0x14001fcbe  cmp     qword ptr [rdi+60h], 0
0x14001fcc3  lea     rdx, aItemDataNameIm_0; "\t<Item>\r\n\t\t<Data name='image'>%s</"...
0x14001fcca  mov     ecx, r8d
0x14001fccd  xorps   xmm1, xmm1
0x14001fcd0  mov     dword ptr [rsp+98h+var_50], r9d
0x14001fcd5  lea     r8, asc_140049BB4; "-"
0x14001fcdc  mov     r9d, [rdi+78h]
0x14001fce0  movsd   [rsp+98h+var_58], xmm2
0x14001fce6  cvtsi2sd xmm1, rcx
0x14001fceb  mov     dword ptr [rsp+98h+var_60], eax
0x14001fcef  lea     rcx, asc_140049BB4; "-"
0x14001fcf6  cmovnz  rcx, [rdi+60h]
0x14001fcfb  cmp     qword ptr [rdi+68h], 0
0x14001fd00  cmovnz  r8, [rdi+68h]
0x14001fd05  divsd   xmm1, xmm0
0x14001fd09  movsd   [rsp+98h+var_68], xmm1
0x14001fd0f  movaps  xmm0, xmm1
0x14001fd12  addsd   xmm0, xmm2
0x14001fd16  movsd   [rsp+98h+var_70], xmm0
0x14001fd1c  mov     [rsp+98h+var_78], rcx
0x14001fd21  mov     rcx, r13; struct _iobuf *
0x14001fd24  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x14001fd29  mov     rbx, [rbx]
0x14001fd2c  cmp     rbx, r14
0x14001fd2f  jnz     loc_14001FC38
0x14001fd35  lea     r11, qword_140082130
0x14001fd3c  mov     rdi, [rdi]
0x14001fd3f  cmp     rdi, r11
0x14001fd42  jnz     loc_14001FC28
0x14001fd48  mov     rdi, cs:qword_140082130
0x14001fd4f  lea     rbx, qword_140082140
0x14001fd56  mov     rsi, [rsi]
0x14001fd59  cmp     rsi, rbx
0x14001fd5c  jnz     loc_14001FC1B
0x14001fd62  add     rsp, 58h
0x14001fd66  pop     r15
0x14001fd68  pop     r14
0x14001fd6a  pop     r13
0x14001fd6c  pop     r12
0x14001fd6e  pop     rdi
0x14001fd6f  pop     rsi
0x14001fd70  pop     rbp
0x14001fd71  pop     rbx
0x14001fd72  retn
```

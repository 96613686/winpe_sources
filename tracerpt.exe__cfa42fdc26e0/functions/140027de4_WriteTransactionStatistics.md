# WriteTransactionStatistics

- ea: `0x140027de4`
- end: `0x140028028`
- name: `WriteTransactionStatistics`
- size: `580`
- prototype: `__int64 __fastcall(struct _iobuf *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140016ae0`

## callees

- `0x140016360`
- `0x1400164c4`
- `0x140027de4`
- `0x140032488`
- `0x140040130`

## string_xrefs

- `0x140027e9a`: `<Table name='transactionStats' key='200' topic='process'>\n<Header>\n  <Threshold type='top' field='count' value='3' />\n  <Threshold type='octave' field='cpu' />\n  <Sort field='cpu' type='number' order='descending'/>\n  <Data name='transaction' class='string'/>\n  <Data name='task' class='number'/>\n  <Data name='responseTime' class='number' format='#,##0'/>\n  <Data name='requestRate' class='number' format='#,##0.0'/>\n  <Data name='kernelCpuPer' class='number' format='#,##0.0'/>\n `
- `0x140027f7d`: `<Item>\n  <Data name='transaction' translate='value'>%s</Data>\n  <Data name='task'>%d</Data>\n  <Data name='count' visible='false'>%d</Data>\n  <Data name='responseTime'>%1.0f</Data>\n  <Data name='requestRate'>%1.2f</Data>\n  <Data name='kernelCpuPer'>%.4f</Data>\n  <Data name='userCpuPer'>%.4f</Data>\n  <Data name='cpu'>%1.2f</Data>\n</Item>\n`

## pseudocode

```c
LPVOID *__fastcall WriteTransactionStatistics(struct _iobuf *a1)
{
  int v1; // r15d
  LPVOID *v2; // rbx
  LPVOID *result; // rax
  double v5; // xmm9_8
  LPVOID *v6; // rdi
  LPVOID *v7; // rsi
  int v8; // ebp
  int v9; // r13d
  double v10; // xmm7_8
  double v11; // xmm8_8
  double v12; // xmm6_8
  double v13; // xmm7_8
  double v14; // xmm8_8
  unsigned __int16 *v15; // rax
  double v16; // xmm10_8
  unsigned int v17; // esi
  double v18; // xmm10_8
  __int64 v19; // [rsp+20h] [rbp-8E8h]
  unsigned __int16 v20[1024]; // [rsp+50h] [rbp-8B8h] BYREF

  v1 = 0;
  v2 = (LPVOID *)qword_140082180;
  result = &qword_140082180;
  v5 = (double)(SystemTimeAsFileTime.dwLowDateTime - CurrentSystem.dwLowDateTime) / 10000000.0;
  if ( &qword_140082180 != qword_140082180 )
  {
    do
    {
      v6 = (LPVOID *)v2[2];
      if ( v6 != v2 + 2 )
      {
        do
        {
          v7 = v6;
          v6 = (LPVOID *)*v6;
          v8 = *((_DWORD *)v7 + 5);
          if ( v8 )
          {
            v9 = *((_DWORD *)v7 + 5);
            if ( !v1 )
            {
              TracerptFPutws(
                (wchar_t *)L"<Table name='transactionStats' key='200' topic='process'>\r\n"
                            "<Header>\r\n"
                            "  <Threshold type='top' field='count' value='3' />\r\n"
                            "  <Threshold type='octave' field='cpu' />\r\n"
                            "  <Sort field='cpu' type='number' order='descending'/>\r\n"
                            "  <Data name='transaction' class='string'/>\r\n"
                            "  <Data name='task' class='number'/>\r\n"
                            "  <Data name='responseTime' class='number' format='#,##0'/>\r\n"
                            "  <Data name='requestRate' class='number' format='#,##0.0'/>\r\n"
                            "  <Data name='kernelCpuPer' class='number' format='#,##0.0'/>\r\n"
                            "  <Data name='userCpuPer' class='number' format='#,##0.0'/>\r\n"
                            "  <Data name='cpu'  summary='total' class='number' format='#,##0.0'/>\r\n"
                            "</Header>\r\n",
                a1);
              v9 = *((_DWORD *)v7 + 5);
              v1 = 1;
            }
            v10 = (double)*((int *)v7 + 18);
            v11 = (double)*((int *)v7 + 19);
            v12 = (v11 + v10) / 1000.0 / v5 * 100.0;
            v13 = v10 / 1000.0 / v5 * 100.0;
            v14 = v11 / 1000.0 / v5 * 100.0;
            if ( dword_14008210C )
            {
              v12 = v12 / (double)dword_14008210C;
              v13 = v13 / (double)dword_14008210C;
              v14 = v14 / (double)dword_14008210C;
            }
            v15 = (unsigned __int16 *)v2[4];
            v16 = (double)(int)v7[5];
            v17 = *((unsigned __int16 *)v7 + 8);
            v18 = v16 / (double)v8;
            if ( !v15 )
              v15 = CpdiGuidToString(v20, 0x400u, (struct _GUID *)v2 + 3);
            LODWORD(v19) = v9;
            TracerptFWPrintf(
              a1,
              (wchar_t *)L"<Item>\r\n"
                          "  <Data name='transaction' translate='value'>%s</Data>\r\n"
                          "  <Data name='task'>%d</Data>\r\n"
                          "  <Data name='count' visible='false'>%d</Data>\r\n"
                          "  <Data name='responseTime'>%1.0f</Data>\r\n"
                          "  <Data name='requestRate'>%1.2f</Data>\r\n"
                          "  <Data name='kernelCpuPer'>%.4f</Data>\r\n"
                          "  <Data name='userCpuPer'>%.4f</Data>\r\n"
                          "  <Data name='cpu'>%1.2f</Data>\r\n"
                          "</Item>\r\n",
              v15,
              v17,
              v19,
              v18,
              (float)v8 / v5,
              v14,
              v13,
              v12);
          }
        }
        while ( v6 != v2 + 2 );
        result = &qword_140082180;
      }
      v2 = (LPVOID *)*v2;
    }
    while ( &qword_140082180 != v2 );
    if ( v1 )
      return (LPVOID *)TracerptFPutws((wchar_t *)L"</Table>\r\n", a1);
  }
  return result;
}

```

## disassembly

```asm
0x140027de4  mov     rax, rsp
0x140027de7  push    rbx
0x140027de8  push    rbp
0x140027de9  push    rsi
0x140027dea  push    rdi
0x140027deb  push    r12
0x140027ded  push    r13
0x140027def  push    r14
0x140027df1  push    r15
0x140027df3  sub     rsp, 8C8h
0x140027dfa  movaps  xmmword ptr [rax-58h], xmm6
0x140027dfe  movaps  xmmword ptr [rax-68h], xmm7
0x140027e02  movaps  xmmword ptr [rax-78h], xmm8
0x140027e07  movaps  xmmword ptr [rax-88h], xmm9
0x140027e0f  movaps  xmmword ptr [rax-98h], xmm10
0x140027e17  movaps  xmmword ptr [rax-0A8h], xmm11
0x140027e1f  mov     rax, cs:__security_cookie
0x140027e26  xor     rax, rsp
0x140027e29  mov     [rsp+908h+var_B8], rax
0x140027e31  mov     rax, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x140027e38  xorps   xmm9, xmm9
0x140027e3c  sub     rax, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x140027e43  xor     r15d, r15d
0x140027e46  mov     rbx, cs:qword_140082180
0x140027e4d  mov     r12, rcx
0x140027e50  cvtsi2sd xmm9, rax
0x140027e55  lea     rax, qword_140082180
0x140027e5c  divsd   xmm9, cs:__real@416312d000000000
0x140027e65  cmp     rax, rbx
0x140027e68  jz      loc_140027FE2
0x140027e6e  lea     r14, [rbx+10h]
0x140027e72  mov     rdi, [r14]
0x140027e75  cmp     rdi, r14
0x140027e78  jz      loc_140027FC2
0x140027e7e  lea     rsi, [rdi]
0x140027e81  mov     rdi, [rdi]
0x140027e84  mov     ebp, [rsi+14h]
0x140027e87  test    ebp, ebp
0x140027e89  jz      loc_140027FB2
0x140027e8f  mov     r13d, ebp
0x140027e92  test    r15d, r15d
0x140027e95  jnz     short loc_140027EB0
0x140027e97  mov     rdx, r12; struct _iobuf *
0x140027e9a  lea     rcx, aTableNameTrans; "<Table name='transactionStats' key='200"...
0x140027ea1  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140027ea6  mov     r13d, [rsi+14h]
0x140027eaa  mov     r15d, 1
0x140027eb0  mov     eax, [rsi+48h]
0x140027eb3  xorps   xmm8, xmm8
0x140027eb7  xorps   xmm7, xmm7
0x140027eba  cvtsi2sd xmm7, rax
0x140027ebf  mov     eax, [rsi+4Ch]
0x140027ec2  cvtsi2sd xmm8, rax
0x140027ec7  mov     eax, cs:dword_14008210C
0x140027ecd  movaps  xmm6, xmm8
0x140027ed1  addsd   xmm6, xmm7
0x140027ed5  divsd   xmm7, cs:__real@408f400000000000
0x140027edd  divsd   xmm6, cs:__real@408f400000000000
0x140027ee5  divsd   xmm8, cs:__real@408f400000000000
0x140027eee  divsd   xmm6, xmm9
0x140027ef3  divsd   xmm7, xmm9
0x140027ef8  mulsd   xmm6, cs:__real@4059000000000000
0x140027f00  mulsd   xmm7, cs:__real@4059000000000000
0x140027f08  divsd   xmm8, xmm9
0x140027f0d  mulsd   xmm8, cs:__real@4059000000000000
0x140027f16  test    eax, eax
0x140027f18  jz      short loc_140027F2F
0x140027f1a  xorps   xmm0, xmm0
0x140027f1d  cvtsi2sd xmm0, rax
0x140027f22  divsd   xmm6, xmm0
0x140027f26  divsd   xmm7, xmm0
0x140027f2a  divsd   xmm8, xmm0
0x140027f2f  mov     rax, [rbx+20h]
0x140027f33  xorps   xmm0, xmm0
0x140027f36  xorps   xmm10, xmm10
0x140027f3a  cvtsi2sd xmm10, qword ptr [rsi+28h]
0x140027f40  movzx   esi, word ptr [rsi+10h]
0x140027f44  cvtsi2sd xmm0, rbp
0x140027f49  divsd   xmm10, xmm0
0x140027f4e  xorps   xmm0, xmm0
0x140027f51  cvtsi2ss xmm0, rbp
0x140027f56  cvtps2pd xmm11, xmm0
0x140027f5a  divsd   xmm11, xmm9
0x140027f5f  test    rax, rax
0x140027f62  jnz     short loc_140027F77
0x140027f64  lea     r8, [rbx+30h]; struct _GUID *
0x140027f68  mov     edx, 400h; unsigned int
0x140027f6d  lea     rcx, [rsp+908h+var_8B8]; unsigned __int16 *
0x140027f72  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x140027f77  movsd   [rsp+908h+var_8C0], xmm6
0x140027f7d  lea     rdx, aItemDataNameTr_1; "<Item>\r\n  <Data name='transaction' tr"...
0x140027f84  movsd   [rsp+908h+var_8C8], xmm7
0x140027f8a  mov     r9d, esi
0x140027f8d  movsd   [rsp+908h+var_8D0], xmm8
0x140027f94  mov     r8, rax
0x140027f97  movsd   [rsp+908h+var_8D8], xmm11
0x140027f9e  mov     rcx, r12; struct _iobuf *
0x140027fa1  movsd   [rsp+908h+var_8E0], xmm10
0x140027fa8  mov     dword ptr [rsp+908h+var_8E8], r13d
0x140027fad  call    ?TracerptFWPrintf@@YAKPEAU_iobuf@@PEBGZZ; TracerptFWPrintf(_iobuf *,ushort const *,...)
0x140027fb2  cmp     rdi, r14
0x140027fb5  jnz     loc_140027E7E
0x140027fbb  lea     rax, qword_140082180
0x140027fc2  mov     rbx, [rbx]
0x140027fc5  cmp     rax, rbx
0x140027fc8  jnz     loc_140027E6E
0x140027fce  test    r15d, r15d
0x140027fd1  jz      short loc_140027FE2
0x140027fd3  mov     rdx, r12; struct _iobuf *
0x140027fd6  lea     rcx, aTable_0; "</Table>\r\n"
0x140027fdd  call    ?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z; TracerptFPutws(ushort const *,_iobuf *)
0x140027fe2  mov     rcx, [rsp+908h+var_B8]
0x140027fea  xor     rcx, rsp; StackCookie
0x140027fed  call    __security_check_cookie
0x140027ff2  lea     r11, [rsp+908h+var_40]
0x140027ffa  movaps  xmm6, xmmword ptr [r11-18h]
0x140027fff  movaps  xmm7, xmmword ptr [r11-28h]
0x140028004  movaps  xmm8, xmmword ptr [r11-38h]
0x140028009  movaps  xmm9, xmmword ptr [r11-48h]
0x14002800e  movaps  xmm10, xmmword ptr [r11-58h]
0x140028013  movaps  xmm11, xmmword ptr [r11-68h]
0x140028018  mov     rsp, r11
0x14002801b  pop     r15
0x14002801d  pop     r14
0x14002801f  pop     r13
0x140028021  pop     r12
0x140028023  pop     rdi
0x140028024  pop     rsi
0x140028025  pop     rbp
0x140028026  pop     rbx
0x140028027  retn
```

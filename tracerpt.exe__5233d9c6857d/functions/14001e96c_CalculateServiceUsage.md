# CalculateServiceUsage

- ea: `0x14001e96c`
- end: `0x14001ebbe`
- name: `CalculateServiceUsage`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140016ae0`

## callees

- `0x14001e96c`

## pseudocode

```c
void CalculateServiceUsage()
{
  struct _PROCESS_RECORD *v0; // r9
  int v1; // ebx
  double v2; // xmm2_8
  __int64 *i; // rcx
  _DWORD *v4; // rdx
  __int64 *v5; // r10
  double v6; // xmm3_8
  int v7; // edx
  int v8; // r8d
  int v9; // eax
  double v10; // xmm0_8
  int v11; // eax
  double v12; // xmm1_8
  double v13; // xmm0_8
  int v14; // eax

  v0 = qword_140082130;
  if ( qword_140082130 != (struct _PROCESS_RECORD *)&qword_140082130 )
  {
    v1 = 1;
    if ( dword_14008210C )
      v1 = dword_14008210C;
    v2 = (double)(SystemTimeAsFileTime.dwLowDateTime - CurrentSystem.dwLowDateTime) / 10000000.0;
    do
    {
      for ( i = (__int64 *)*((_QWORD *)v0 + 2); i != (__int64 *)((char *)v0 + 16); i = (__int64 *)*i )
      {
        v4 = (_DWORD *)i[12];
        if ( v4 )
        {
          v4[19] += dword_1400820F8 * (*((_DWORD *)i + 49) - *((_DWORD *)i + 48));
          v4[18] += dword_1400820F8 * (*((_DWORD *)i + 47) - *((_DWORD *)i + 46));
          if ( *((_DWORD *)i + 30)
            || *((_DWORD *)i + 31)
            || *((_DWORD *)i + 47) > *((_DWORD *)i + 46)
            || *((_DWORD *)i + 49) > *((_DWORD *)i + 48)
            || *((_DWORD *)i + 32)
            || *((_DWORD *)i + 33)
            || *((_DWORD *)i + 36) )
          {
            ++v4[27];
          }
          ++v4[26];
          v4[28] += *((_DWORD *)i + 30) + *((_DWORD *)i + 36);
          v4[30] += *((_DWORD *)i + 38) + *((_DWORD *)i + 40);
          v4[29] += *((_DWORD *)i + 31);
          v4[31] += *((_DWORD *)i + 39);
          v4[32] += *((_DWORD *)i + 37);
          v4[4] += *((_DWORD *)i + 141);
        }
      }
      v5 = (__int64 *)*((_QWORD *)v0 + 4);
      if ( v5 != (__int64 *)((char *)v0 + 32) )
      {
        v6 = (double)v1;
        do
        {
          v7 = *((_DWORD *)v5 + 18);
          v8 = *((_DWORD *)v5 + 19);
          v9 = *((_DWORD *)v5 + 28);
          *((double *)v5 + 11) = ((double)v7 + 0.0) / v2 / 1000.0 * 100.0 / v6;
          *((double *)v5 + 10) = ((double)(v8 + v7) + 0.0) / v2 / 1000.0 * 100.0 / v6;
          *((double *)v5 + 12) = ((double)v8 + 0.0) / v2 / 1000.0 * 100.0 / v6;
          v10 = (double)v9;
          v11 = *((_DWORD *)v5 + 32);
          v12 = (double)*((int *)v5 + 29) / v2;
          *((double *)v5 + 17) = v10 / v2;
          *((double *)v5 + 18) = v12;
          v13 = (double)v11;
          v14 = *((_DWORD *)v5 + 4);
          *((double *)v5 + 19) = v13 / v2;
          *((double *)v5 + 3) = (double)v14 / v2;
          v5 = (__int64 *)*v5;
        }
        while ( v5 != (__int64 *)((char *)v0 + 32) );
      }
      v0 = *(struct _PROCESS_RECORD **)v0;
    }
    while ( v0 != (struct _PROCESS_RECORD *)&qword_140082130 );
  }
}

```

## disassembly

```asm
0x14001e96c  mov     [rsp+arg_0], rbx
0x14001e971  mov     [rsp+arg_8], rsi
0x14001e976  mov     r9, cs:qword_140082130
0x14001e97d  lea     rsi, qword_140082130
0x14001e984  cmp     r9, rsi
0x14001e987  jz      loc_14001EBB3
0x14001e98d  mov     eax, cs:dword_14008210C
0x14001e993  xorps   xmm2, xmm2
0x14001e996  movsd   xmm5, cs:__real@408f400000000000
0x14001e99e  test    eax, eax
0x14001e9a0  mov     ebx, 1
0x14001e9a5  xorps   xmm4, xmm4
0x14001e9a8  cmovnz  ebx, eax
0x14001e9ab  mov     rax, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x14001e9b2  sub     rax, qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime; _SYSTEM_RECORD CurrentSystem ...
0x14001e9b9  cvtsi2sd xmm2, rax
0x14001e9be  divsd   xmm2, cs:__real@416312d000000000
0x14001e9c6  lea     r8, [r9+10h]
0x14001e9ca  mov     rcx, [r8]
0x14001e9cd  jmp     loc_14001EA96
0x14001e9d2  mov     rdx, [rcx+60h]
0x14001e9d6  test    rdx, rdx
0x14001e9d9  jz      loc_14001EA93
0x14001e9df  mov     eax, [rcx+0C4h]
0x14001e9e5  sub     eax, [rcx+0C0h]
0x14001e9eb  imul    eax, cs:dword_1400820F8
0x14001e9f2  add     [rdx+4Ch], eax
0x14001e9f5  mov     eax, [rcx+0BCh]
0x14001e9fb  sub     eax, [rcx+0B8h]
0x14001ea01  imul    eax, cs:dword_1400820F8
0x14001ea08  add     [rdx+48h], eax
0x14001ea0b  cmp     dword ptr [rcx+78h], 0
0x14001ea0f  jnz     short loc_14001EA4E
0x14001ea11  cmp     dword ptr [rcx+7Ch], 0
0x14001ea15  jnz     short loc_14001EA4E
0x14001ea17  mov     eax, [rcx+0B8h]
0x14001ea1d  cmp     [rcx+0BCh], eax
0x14001ea23  ja      short loc_14001EA4E
0x14001ea25  mov     eax, [rcx+0C0h]
0x14001ea2b  cmp     [rcx+0C4h], eax
0x14001ea31  ja      short loc_14001EA4E
0x14001ea33  cmp     dword ptr [rcx+80h], 0
0x14001ea3a  jnz     short loc_14001EA4E
0x14001ea3c  cmp     dword ptr [rcx+84h], 0
0x14001ea43  jnz     short loc_14001EA4E
0x14001ea45  cmp     dword ptr [rcx+90h], 0
0x14001ea4c  jz      short loc_14001EA51
0x14001ea4e  inc     dword ptr [rdx+6Ch]
0x14001ea51  inc     dword ptr [rdx+68h]
0x14001ea54  mov     eax, [rcx+90h]
0x14001ea5a  add     eax, [rcx+78h]
0x14001ea5d  add     [rdx+70h], eax
0x14001ea60  mov     eax, [rcx+0A0h]
0x14001ea66  add     eax, [rcx+98h]
0x14001ea6c  add     [rdx+78h], eax
0x14001ea6f  mov     eax, [rcx+7Ch]
0x14001ea72  add     [rdx+74h], eax
0x14001ea75  mov     eax, [rcx+9Ch]
0x14001ea7b  add     [rdx+7Ch], eax
0x14001ea7e  mov     eax, [rcx+94h]
0x14001ea84  add     [rdx+80h], eax
0x14001ea8a  mov     eax, [rcx+234h]
0x14001ea90  add     [rdx+10h], eax
0x14001ea93  mov     rcx, [rcx]
0x14001ea96  cmp     rcx, r8
0x14001ea99  jnz     loc_14001E9D2
0x14001ea9f  lea     r11, [r9+20h]
0x14001eaa3  mov     r10, [r11]
0x14001eaa6  cmp     r10, r11
0x14001eaa9  jz      loc_14001EBA7
0x14001eaaf  mov     eax, ebx
0x14001eab1  xorps   xmm3, xmm3
0x14001eab4  cvtsi2sd xmm3, rax
0x14001eab9  mov     edx, [r10+48h]
0x14001eabd  xorps   xmm0, xmm0
0x14001eac0  mov     r8d, [r10+4Ch]
0x14001eac4  xorps   xmm1, xmm1
0x14001eac7  mov     eax, [r10+70h]
0x14001eacb  cvtsi2sd xmm1, rdx
0x14001ead0  lea     ecx, [r8+rdx]
0x14001ead4  cvtsi2sd xmm0, rcx
0x14001ead9  addsd   xmm1, xmm4
0x14001eadd  addsd   xmm0, xmm4
0x14001eae1  divsd   xmm1, xmm2
0x14001eae5  divsd   xmm0, xmm2
0x14001eae9  divsd   xmm1, xmm5
0x14001eaed  divsd   xmm0, xmm5
0x14001eaf1  mulsd   xmm1, cs:__real@4059000000000000
0x14001eaf9  mulsd   xmm0, cs:__real@4059000000000000
0x14001eb01  divsd   xmm1, xmm3
0x14001eb05  divsd   xmm0, xmm3
0x14001eb09  movsd   qword ptr [r10+58h], xmm1
0x14001eb0f  xorps   xmm1, xmm1
0x14001eb12  movsd   qword ptr [r10+50h], xmm0
0x14001eb18  xorps   xmm0, xmm0
0x14001eb1b  cvtsi2sd xmm0, r8
0x14001eb20  addsd   xmm0, xmm4
0x14001eb24  divsd   xmm0, xmm2
0x14001eb28  divsd   xmm0, xmm5
0x14001eb2c  mulsd   xmm0, cs:__real@4059000000000000
0x14001eb34  divsd   xmm0, xmm3
0x14001eb38  movsd   qword ptr [r10+60h], xmm0
0x14001eb3e  xorps   xmm0, xmm0
0x14001eb41  cvtsi2sd xmm0, rax
0x14001eb46  mov     eax, [r10+74h]
0x14001eb4a  cvtsi2sd xmm1, rax
0x14001eb4f  mov     eax, [r10+80h]
0x14001eb56  divsd   xmm0, xmm2
0x14001eb5a  divsd   xmm1, xmm2
0x14001eb5e  movsd   qword ptr [r10+88h], xmm0
0x14001eb67  xorps   xmm0, xmm0
0x14001eb6a  movsd   qword ptr [r10+90h], xmm1
0x14001eb73  xorps   xmm1, xmm1
0x14001eb76  cvtsi2sd xmm0, rax
0x14001eb7b  mov     eax, [r10+10h]
0x14001eb7f  cvtsi2sd xmm1, rax
0x14001eb84  divsd   xmm0, xmm2
0x14001eb88  divsd   xmm1, xmm2
0x14001eb8c  movsd   qword ptr [r10+98h], xmm0
0x14001eb95  movsd   qword ptr [r10+18h], xmm1
0x14001eb9b  mov     r10, [r10]
0x14001eb9e  cmp     r10, r11
0x14001eba1  jnz     loc_14001EAB9
0x14001eba7  mov     r9, [r9]
0x14001ebaa  cmp     r9, rsi
0x14001ebad  jnz     loc_14001E9C6
0x14001ebb3  mov     rbx, [rsp+arg_0]
0x14001ebb8  mov     rsi, [rsp+arg_8]
0x14001ebbd  retn
```

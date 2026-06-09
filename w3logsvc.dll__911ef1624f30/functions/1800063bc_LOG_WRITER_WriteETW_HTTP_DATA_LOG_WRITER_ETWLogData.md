# LOG_WRITER::WriteETW(HTTP_DATA *,LOG_WRITER::ETWLogData *)

- ea: `0x1800063bc`
- end: `0x18000673b`
- name: `?WriteETW@LOG_WRITER@@AEAAJPEAUHTTP_DATA@@PEAUETWLogData@1@@Z`
- size: `895`
- prototype: `__int64 __fastcall(LOG_WRITER *__hidden this, struct HTTP_DATA *, struct LOG_WRITER::ETWLogData *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003718`

## callees

- `0x1800063bc`
- `0x1800067a4`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800063ec`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000640e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000642e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000644e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000646e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000648e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800064ae`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800064ce`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800064ee`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800063ec`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000640e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000642e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000644e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000646e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000648e`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800064ae`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800064ce`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x1800064ee`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180006515`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180006535`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180006555`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180006575`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180006595`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x1800065b5`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180006515`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180006535`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180006555`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180006575`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x180006595`
- `iisutil!?Copy@STRA@@QEAAJAEBV1@@Z` at `0x1800065b5`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800065e7`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800065e7`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::WriteETW(LOG_WRITER *this, struct HTTP_DATA *a2, struct LOG_WRITER::ETWLogData *a3)
{
  int v6; // ebx
  int v7; // eax
  __int64 v8; // rdx
  _WORD *v9; // rcx

  if ( *((_DWORD *)a3 + 14) )
  {
    v6 = 0;
  }
  else
  {
    v6 = STRU::Copy((struct LOG_WRITER::ETWLogData *)((char *)a3 + 8), (LOG_WRITER *)((char *)this + 560));
    if ( v6 < 0 )
      return (unsigned int)v6;
  }
  if ( *((_DWORD *)a3 + 34)
    || (v6 = STRU::Copy((struct LOG_WRITER::ETWLogData *)((char *)a3 + 88), (LOG_WRITER *)((char *)this + 560)), v6 >= 0) )
  {
    if ( *((_DWORD *)a3 + 54)
      || (v6 = STRU::Copy((struct LOG_WRITER::ETWLogData *)((char *)a3 + 168), (LOG_WRITER *)((char *)this + 560)),
          v6 >= 0) )
    {
      if ( *((_DWORD *)a3 + 98)
        || (v6 = STRU::Copy((struct LOG_WRITER::ETWLogData *)((char *)a3 + 344), (LOG_WRITER *)((char *)this + 560)),
            v6 >= 0) )
      {
        if ( *((_DWORD *)a3 + 142)
          || (v6 = STRU::Copy((struct LOG_WRITER::ETWLogData *)((char *)a3 + 520), (LOG_WRITER *)((char *)this + 560)),
              v6 >= 0) )
        {
          if ( *((_DWORD *)a3 + 164)
            || (v6 = STRU::Copy((struct LOG_WRITER::ETWLogData *)((char *)a3 + 608), (LOG_WRITER *)((char *)this + 560)),
                v6 >= 0) )
          {
            if ( *((_DWORD *)a3 + 194)
              || (v6 = STRU::Copy(
                         (struct LOG_WRITER::ETWLogData *)((char *)a3 + 728),
                         (LOG_WRITER *)((char *)this + 560)),
                  v6 >= 0) )
            {
              if ( *((_DWORD *)a3 + 214)
                || (v6 = STRU::Copy(
                           (struct LOG_WRITER::ETWLogData *)((char *)a3 + 808),
                           (LOG_WRITER *)((char *)this + 560)),
                    v6 >= 0) )
              {
                if ( *((_DWORD *)a3 + 244)
                  || (v6 = STRU::Copy(
                             (struct LOG_WRITER::ETWLogData *)((char *)a3 + 928),
                             (LOG_WRITER *)((char *)this + 560)),
                      v6 >= 0) )
                {
                  if ( *((_DWORD *)a3 + 352)
                    || (v6 = STRA::Copy(
                               (struct LOG_WRITER::ETWLogData *)((char *)a3 + 1360),
                               (LOG_WRITER *)((char *)this + 496)),
                        v6 >= 0) )
                  {
                    if ( *((_DWORD *)a3 + 374)
                      || (v6 = STRA::Copy(
                                 (struct LOG_WRITER::ETWLogData *)((char *)a3 + 1448),
                                 (LOG_WRITER *)((char *)this + 496)),
                          v6 >= 0) )
                    {
                      if ( *((_DWORD *)a3 + 396)
                        || (v6 = STRA::Copy(
                                   (struct LOG_WRITER::ETWLogData *)((char *)a3 + 1536),
                                   (LOG_WRITER *)((char *)this + 496)),
                            v6 >= 0) )
                      {
                        if ( *((_DWORD *)a3 + 418)
                          || (v6 = STRA::Copy(
                                     (struct LOG_WRITER::ETWLogData *)((char *)a3 + 1624),
                                     (LOG_WRITER *)((char *)this + 496)),
                              v6 >= 0) )
                        {
                          if ( *((_DWORD *)a3 + 440)
                            || (v6 = STRA::Copy(
                                       (struct LOG_WRITER::ETWLogData *)((char *)a3 + 1712),
                                       (LOG_WRITER *)((char *)this + 496)),
                                v6 >= 0) )
                          {
                            if ( *((_DWORD *)a3 + 458)
                              || (v6 = STRA::Copy(
                                         (struct LOG_WRITER::ETWLogData *)((char *)a3 + 1784),
                                         (LOG_WRITER *)((char *)this + 496)),
                                  v6 >= 0) )
                            {
                              v7 = *((_DWORD *)a3 + 274);
                              if ( v7 )
                              {
                                v8 = (unsigned int)(v7 - 1);
                                if ( *(_WORD *)(*((_QWORD *)a3 + 135) + 2 * v8) == 32 )
                                  STRU::SetLen((struct LOG_WRITER::ETWLogData *)((char *)a3 + 1048), v8);
                              }
                              if ( (Microsoft_Windows_IIS_LoggingEnableBits & 1) != 0 )
                              {
                                v9 = (_WORD *)*((_QWORD *)a2 + 3);
                                McTemplateU0qzzzzzzzszshqxxxhssszshz_EventWriteTransfer(
                                  (_DWORD)v9,
                                  *((_QWORD *)a2 + 9),
                                  *(_DWORD *)a3,
                                  *((_QWORD *)a3 + 5),
                                  *((_QWORD *)a3 + 15),
                                  *((_QWORD *)a3 + 25),
                                  *((_QWORD *)a3 + 120),
                                  *((_QWORD *)a3 + 80),
                                  *((_QWORD *)a3 + 69),
                                  *((_QWORD *)a3 + 47),
                                  *((_QWORD *)a3 + 218),
                                  *((_QWORD *)a3 + 105),
                                  *((_QWORD *)a3 + 207),
                                  **((_WORD **)a2 + 2),
                                  **((_DWORD **)a2 + 4),
                                  **((_QWORD **)a2 + 7),
                                  **((_QWORD **)a2 + 8),
                                  **((_QWORD **)a2 + 9),
                                  *((_WORD *)a3 + 936),
                                  *((_QWORD *)a3 + 174),
                                  *((_QWORD *)a3 + 185),
                                  *((_QWORD *)a3 + 196),
                                  *((_QWORD *)a3 + 95),
                                  *((_QWORD *)a3 + 227),
                                  *v9,
                                  *((_QWORD *)a3 + 135));
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800063bc  push    rbx
0x1800063be  push    rbp
0x1800063bf  push    rsi
0x1800063c0  push    rdi
0x1800063c1  push    r14
0x1800063c3  push    r15
0x1800063c5  sub     rsp, 0D8h
0x1800063cc  mov     rbp, rcx
0x1800063cf  xor     r15d, r15d
0x1800063d2  lea     rcx, [r8+8]
0x1800063d6  mov     rdi, r8
0x1800063d9  mov     r14, rdx
0x1800063dc  lea     rsi, [rbp+230h]
0x1800063e3  cmp     [rcx+30h], r15d
0x1800063e7  jnz     short loc_1800063FE
0x1800063e9  mov     rdx, rsi
0x1800063ec  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800063f2  mov     ebx, eax
0x1800063f4  test    eax, eax
0x1800063f6  js      loc_180006729
0x1800063fc  jmp     short loc_180006401
0x1800063fe  mov     ebx, r15d
0x180006401  lea     rcx, [rdi+58h]
0x180006405  cmp     [rcx+30h], r15d
0x180006409  jnz     short loc_18000641E
0x18000640b  mov     rdx, rsi
0x18000640e  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180006414  mov     ebx, eax
0x180006416  test    eax, eax
0x180006418  js      loc_180006729
0x18000641e  lea     rcx, [rdi+0A8h]
0x180006425  cmp     [rcx+30h], r15d
0x180006429  jnz     short loc_18000643E
0x18000642b  mov     rdx, rsi
0x18000642e  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180006434  mov     ebx, eax
0x180006436  test    eax, eax
0x180006438  js      loc_180006729
0x18000643e  lea     rcx, [rdi+158h]
0x180006445  cmp     [rcx+30h], r15d
0x180006449  jnz     short loc_18000645E
0x18000644b  mov     rdx, rsi
0x18000644e  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180006454  mov     ebx, eax
0x180006456  test    eax, eax
0x180006458  js      loc_180006729
0x18000645e  lea     rcx, [rdi+208h]
0x180006465  cmp     [rcx+30h], r15d
0x180006469  jnz     short loc_18000647E
0x18000646b  mov     rdx, rsi
0x18000646e  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180006474  mov     ebx, eax
0x180006476  test    eax, eax
0x180006478  js      loc_180006729
0x18000647e  lea     rcx, [rdi+260h]
0x180006485  cmp     [rcx+30h], r15d
0x180006489  jnz     short loc_18000649E
0x18000648b  mov     rdx, rsi
0x18000648e  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180006494  mov     ebx, eax
0x180006496  test    eax, eax
0x180006498  js      loc_180006729
0x18000649e  lea     rcx, [rdi+2D8h]
0x1800064a5  cmp     [rcx+30h], r15d
0x1800064a9  jnz     short loc_1800064BE
0x1800064ab  mov     rdx, rsi
0x1800064ae  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800064b4  mov     ebx, eax
0x1800064b6  test    eax, eax
0x1800064b8  js      loc_180006729
0x1800064be  lea     rcx, [rdi+328h]
0x1800064c5  cmp     [rcx+30h], r15d
0x1800064c9  jnz     short loc_1800064DE
0x1800064cb  mov     rdx, rsi
0x1800064ce  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800064d4  mov     ebx, eax
0x1800064d6  test    eax, eax
0x1800064d8  js      loc_180006729
0x1800064de  lea     rcx, [rdi+3A0h]
0x1800064e5  cmp     [rcx+30h], r15d
0x1800064e9  jnz     short loc_1800064FE
0x1800064eb  mov     rdx, rsi
0x1800064ee  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800064f4  mov     ebx, eax
0x1800064f6  test    eax, eax
0x1800064f8  js      loc_180006729
0x1800064fe  lea     rcx, [rdi+550h]
0x180006505  lea     rsi, [rbp+1F0h]
0x18000650c  cmp     [rcx+30h], r15d
0x180006510  jnz     short loc_180006525
0x180006512  mov     rdx, rsi
0x180006515  call    cs:__imp_?Copy@STRA@@QEAAJAEBV1@@Z; STRA::Copy(STRA const &)
0x18000651b  mov     ebx, eax
0x18000651d  test    eax, eax
0x18000651f  js      loc_180006729
0x180006525  lea     rcx, [rdi+5A8h]
0x18000652c  cmp     [rcx+30h], r15d
0x180006530  jnz     short loc_180006545
0x180006532  mov     rdx, rsi
0x180006535  call    cs:__imp_?Copy@STRA@@QEAAJAEBV1@@Z; STRA::Copy(STRA const &)
0x18000653b  mov     ebx, eax
0x18000653d  test    eax, eax
0x18000653f  js      loc_180006729
0x180006545  lea     rcx, [rdi+600h]
0x18000654c  cmp     [rcx+30h], r15d
0x180006550  jnz     short loc_180006565
0x180006552  mov     rdx, rsi
0x180006555  call    cs:__imp_?Copy@STRA@@QEAAJAEBV1@@Z; STRA::Copy(STRA const &)
0x18000655b  mov     ebx, eax
0x18000655d  test    eax, eax
0x18000655f  js      loc_180006729
0x180006565  lea     rcx, [rdi+658h]
0x18000656c  cmp     [rcx+30h], r15d
0x180006570  jnz     short loc_180006585
0x180006572  mov     rdx, rsi
0x180006575  call    cs:__imp_?Copy@STRA@@QEAAJAEBV1@@Z; STRA::Copy(STRA const &)
0x18000657b  mov     ebx, eax
0x18000657d  test    eax, eax
0x18000657f  js      loc_180006729
0x180006585  lea     rcx, [rdi+6B0h]
0x18000658c  cmp     [rcx+30h], r15d
0x180006590  jnz     short loc_1800065A5
0x180006592  mov     rdx, rsi
0x180006595  call    cs:__imp_?Copy@STRA@@QEAAJAEBV1@@Z; STRA::Copy(STRA const &)
0x18000659b  mov     ebx, eax
0x18000659d  test    eax, eax
0x18000659f  js      loc_180006729
0x1800065a5  lea     rcx, [rdi+6F8h]
0x1800065ac  cmp     [rcx+30h], r15d
0x1800065b0  jnz     short loc_1800065C5
0x1800065b2  mov     rdx, rsi
0x1800065b5  call    cs:__imp_?Copy@STRA@@QEAAJAEBV1@@Z; STRA::Copy(STRA const &)
0x1800065bb  mov     ebx, eax
0x1800065bd  test    eax, eax
0x1800065bf  js      loc_180006729
0x1800065c5  mov     eax, [rdi+448h]
0x1800065cb  test    eax, eax
0x1800065cd  jz      short loc_1800065ED
0x1800065cf  lea     edx, [rax-1]
0x1800065d2  mov     rax, [rdi+438h]
0x1800065d9  cmp     word ptr [rax+rdx*2], 20h ; ' '
0x1800065de  jnz     short loc_1800065ED
0x1800065e0  lea     rcx, [rdi+418h]
0x1800065e7  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x1800065ed  test    cs:Microsoft_Windows_IIS_LoggingEnableBits, 1
0x1800065f4  jz      loc_180006729
0x1800065fa  mov     rax, [rdi+438h]
0x180006601  mov     [rsp+108h+var_40], rax
0x180006609  mov     r8, [r14+40h]
0x18000660d  mov     r9, [r14+38h]
0x180006611  mov     rcx, [r14+18h]
0x180006615  mov     rdx, [r14+48h]
0x180006619  mov     r10, [r14+20h]
0x18000661d  mov     r11, [r14+10h]
0x180006621  movzx   eax, word ptr [rcx]
0x180006624  mov     [rsp+108h+var_48], ax
0x18000662c  mov     rax, [rdi+718h]
0x180006633  mov     [rsp+108h+var_50], rax
0x18000663b  mov     rax, [rdi+2F8h]
0x180006642  mov     [rsp+108h+var_58], rax
0x18000664a  mov     rax, [rdi+620h]
0x180006651  mov     [rsp+108h+var_60], rax
0x180006659  mov     rax, [rdi+5C8h]
0x180006660  mov     [rsp+108h+var_68], rax
0x180006668  mov     rax, [rdi+570h]
0x18000666f  mov     [rsp+108h+var_70], rax
0x180006677  movzx   eax, word ptr [rdi+750h]
0x18000667e  mov     [rsp+108h+var_78], ax
0x180006686  mov     rax, [rdx]
0x180006689  mov     [rsp+108h+var_80], rax
0x180006691  mov     rax, [r8]
0x180006694  mov     r8d, [rdi]
0x180006697  mov     [rsp+108h+var_88], rax
0x18000669f  mov     rax, [r9]
0x1800066a2  mov     r9, [rdi+28h]
0x1800066a6  mov     [rsp+108h+var_90], rax
0x1800066ab  mov     eax, [r10]
0x1800066ae  mov     [rsp+108h+var_98], eax
0x1800066b2  movzx   eax, word ptr [r11]
0x1800066b6  mov     [rsp+108h+var_A0], ax
0x1800066bb  mov     rax, [rdi+678h]
0x1800066c2  mov     [rsp+108h+var_A8], rax
0x1800066c7  mov     rax, [rdi+348h]
0x1800066ce  mov     [rsp+108h+var_B0], rax
0x1800066d3  mov     rax, [rdi+6D0h]
0x1800066da  mov     [rsp+108h+var_B8], rax
0x1800066df  mov     rax, [rdi+178h]
0x1800066e6  mov     [rsp+108h+var_C0], rax
0x1800066eb  mov     rax, [rdi+228h]
0x1800066f2  mov     [rsp+108h+var_C8], rax
0x1800066f7  mov     rax, [rdi+280h]
0x1800066fe  mov     [rsp+108h+var_D0], rax
0x180006703  mov     rax, [rdi+3C0h]
0x18000670a  mov     [rsp+108h+var_D8], rax
0x18000670f  mov     rax, [rdi+0C8h]
0x180006716  mov     [rsp+108h+var_E0], rax
0x18000671b  mov     rax, [rdi+78h]
0x18000671f  mov     [rsp+108h+var_E8], rax
0x180006724  call    McTemplateU0qzzzzzzzszshqxxxhssszshz_EventWriteTransfer
0x180006729  mov     eax, ebx
0x18000672b  add     rsp, 0D8h
0x180006732  pop     r15
0x180006734  pop     r14
0x180006736  pop     rdi
0x180006737  pop     rsi
0x180006738  pop     rbp
0x180006739  pop     rbx
0x18000673a  retn
```

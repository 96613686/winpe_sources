# HUBMISC_ValidateAndCacheMSOSExtendedPropertyDescriptor

- ea: `0x140033234`
- end: `0x140033527`
- name: `HUBMISC_ValidateAndCacheMSOSExtendedPropertyDescriptor`
- size: `755`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140025440`

## callees

- `0x1400067ac`
- `0x1400083b4`
- `0x140033234`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003328d`
- `ntoskrnl!RtlCompareMemory` at `0x14003328d`

## pseudocode

```c
__int64 __fastcall HUBMISC_ValidateAndCacheMSOSExtendedPropertyDescriptor(unsigned int *a1)
{
  _DWORD *v1; // rdi
  unsigned int *v2; // rbx
  __int64 v3; // rcx
  int v4; // r9d
  unsigned __int16 *v5; // rsi
  int v6; // r10d
  unsigned __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // r8
  int v10; // r11d
  unsigned int v11; // edi

  v1 = a1 + 435;
  v2 = a1;
  if ( a1[66] == a1[435] )
  {
    v5 = (unsigned __int16 *)*((_QWORD *)a1 + 265);
    if ( RtlCompareMemory(a1 + 435, v5, 0xAu) == 10 )
    {
      if ( *v1 <= 0x1000u )
      {
        a1 = (unsigned int *)(v5 + 5);
        v6 = 0;
        v7 = (unsigned __int64)v5 + *(unsigned int *)v5;
        while ( (unsigned __int64)a1 < v7 )
        {
          if ( (unsigned __int64)a1 + 14 > v7 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_31;
            v4 = 73;
            goto LABEL_29;
          }
          v8 = *a1;
          if ( (int)v7 - (int)a1 < (unsigned int)v8 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_31;
            v4 = 74;
            goto LABEL_29;
          }
          if ( (unsigned int)v8 < 0xE )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_31;
            v4 = 75;
            goto LABEL_29;
          }
          if ( a1[1] - 1 > 6 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_31;
            v4 = 76;
            goto LABEL_29;
          }
          v9 = *((unsigned __int16 *)a1 + 4);
          if ( (int)v9 + 14 > (unsigned int)v8 || !*((_WORD *)a1 + 4) || (v9 & 1) != 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_31;
            v4 = 77;
            goto LABEL_29;
          }
          if ( !*((_WORD *)a1 + 5) || *((_WORD *)a1 + ((unsigned __int64)*((unsigned __int16 *)a1 + 4) >> 1) + 4) )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_31;
            v4 = 78;
            goto LABEL_29;
          }
          v10 = *(unsigned int *)((char *)a1 + v9 + 10);
          if ( (unsigned int)v9 > ~v10 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_31;
            v4 = 79;
            goto LABEL_29;
          }
          if ( (unsigned int)(v10 + v9) > 0xFFFFFFF1 || v10 + (int)v9 + 14 > (unsigned int)v8 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_31;
            v4 = 80;
            goto LABEL_29;
          }
          if ( ++v6 == v5[4] )
            break;
          a1 = (unsigned int *)((char *)a1 + v8);
        }
        if ( v6 == v5[4] )
          return 4077;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_31;
        v4 = 81;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_31;
        v4 = 72;
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_31;
      v4 = 71;
    }
LABEL_29:
    v3 = *((_QWORD *)v2 + 1);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_31;
    v3 = *((_QWORD *)a1 + 1);
    v4 = 70;
  }
  WPP_RECORDER_SF_(*(_QWORD *)(v3 + 1432), 2, 5, v4, (__int64)WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids);
LABEL_31:
  v11 = 4065;
  if ( (byte_14006ED41 & 1) != 0 )
    McTemplateK0p_EtwWriteTransfer(
      a1,
      USBHUB3_ETW_EVENT_INVALID_MSOS_EXTENDED_PROPERTY_DESCRIPTOR,
      v2 + 381,
      *((_QWORD *)v2 + 3));
  return v11;
}

```

## disassembly

```asm
0x140033234  mov     [rsp+arg_0], rbx
0x140033239  mov     [rsp+arg_8], rsi
0x14003323e  push    rdi
0x14003323f  sub     rsp, 30h
0x140033243  lea     rdi, [rcx+6CCh]
0x14003324a  mov     rbx, rcx
0x14003324d  mov     eax, [rdi]
0x14003324f  cmp     [rcx+108h], eax
0x140033255  jz      short loc_14003327A
0x140033257  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003325e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033265  jz      loc_1400333F8
0x14003326b  mov     rcx, [rcx+8]
0x14003326f  mov     r9d, 46h ; 'F'
0x140033275  jmp     loc_1400333D8
0x14003327a  mov     rsi, [rcx+848h]
0x140033281  mov     r8d, 0Ah; Length
0x140033287  mov     rdx, rsi; Source2
0x14003328a  mov     rcx, rdi; Source1
0x14003328d  call    cs:__imp_RtlCompareMemory
0x140033294  nop     dword ptr [rax+rax+00h]
0x140033299  cmp     rax, 0Ah
0x14003329d  jz      short loc_1400332BE
0x14003329f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400332a6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400332ad  jz      loc_1400333F8
0x1400332b3  mov     r9d, 47h ; 'G'
0x1400332b9  jmp     loc_1400333D4
0x1400332be  cmp     dword ptr [rdi], 1000h
0x1400332c4  jbe     short loc_1400332E5
0x1400332c6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400332cd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400332d4  jz      loc_1400333F8
0x1400332da  mov     r9d, 48h ; 'H'
0x1400332e0  jmp     loc_1400333D4
0x1400332e5  mov     edx, [rsi]
0x1400332e7  lea     rcx, [rsi+0Ah]
0x1400332eb  xor     edi, edi
0x1400332ed  mov     r10d, edi
0x1400332f0  add     rdx, rsi
0x1400332f3  jmp     loc_1400333A8
0x1400332f8  lea     rax, [rcx+0Eh]
0x1400332fc  cmp     rax, rdx
0x1400332ff  ja      loc_1400334F0
0x140033305  mov     r9d, [rcx]
0x140033308  mov     eax, edx
0x14003330a  sub     eax, ecx
0x14003330c  cmp     eax, r9d
0x14003330f  jb      loc_1400334D1
0x140033315  cmp     r9d, 0Eh
0x140033319  jb      loc_1400334B2
0x14003331f  mov     eax, [rcx+4]
0x140033322  dec     eax
0x140033324  cmp     eax, 6
0x140033327  ja      loc_140033493
0x14003332d  movzx   r8d, word ptr [rcx+8]
0x140033332  lea     eax, [r8+0Eh]
0x140033336  cmp     eax, r9d
0x140033339  ja      loc_140033474
0x14003333f  test    r8d, r8d
0x140033342  jz      loc_140033474
0x140033348  test    r8b, 1
0x14003334c  jnz     loc_140033474
0x140033352  cmp     [rcx+0Ah], di
0x140033356  jz      loc_140033459
0x14003335c  mov     eax, r8d
0x14003335f  shr     rax, 1
0x140033362  cmp     [rcx+rax*2+8], di
0x140033367  jnz     loc_140033459
0x14003336d  mov     r11d, [r8+rcx+0Ah]
0x140033372  mov     eax, r11d
0x140033375  not     eax
0x140033377  cmp     r8d, eax
0x14003337a  ja      loc_14003343E
0x140033380  lea     eax, [r11+r8]
0x140033384  cmp     eax, 0FFFFFFF1h
0x140033387  ja      loc_140033426
0x14003338d  add     eax, 0Eh
0x140033390  cmp     eax, r9d
0x140033393  ja      loc_140033426
0x140033399  movzx   eax, word ptr [rsi+8]
0x14003339d  inc     r10d
0x1400333a0  cmp     r10d, eax
0x1400333a3  jz      short loc_1400333B1
0x1400333a5  add     rcx, r9
0x1400333a8  cmp     rcx, rdx
0x1400333ab  jb      loc_1400332F8
0x1400333b1  movzx   eax, word ptr [rsi+8]
0x1400333b5  cmp     r10d, eax
0x1400333b8  jz      loc_14003350F
0x1400333be  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400333c5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400333cc  jz      short loc_1400333F8
0x1400333ce  mov     r9d, 51h ; 'Q'
0x1400333d4  mov     rcx, [rbx+8]
0x1400333d8  mov     rcx, [rcx+598h]
0x1400333df  lea     rax, WPP_dde998bf8bb3310d95d4227a99ba80b7_Traceguids
0x1400333e6  mov     r8d, 5
0x1400333ec  mov     [rsp+38h+var_18], rax
0x1400333f1  mov     dl, 2
0x1400333f3  call    WPP_RECORDER_SF_
0x1400333f8  test    cs:byte_14006ED41, 1
0x1400333ff  mov     edi, 0FE1h
0x140033404  jz      loc_140033514
0x14003340a  mov     r9, [rbx+18h]
0x14003340e  lea     r8, [rbx+5F4h]
0x140033415  lea     rdx, USBHUB3_ETW_EVENT_INVALID_MSOS_EXTENDED_PROPERTY_DESCRIPTOR
0x14003341c  call    McTemplateK0p_EtwWriteTransfer
0x140033421  jmp     loc_140033514
0x140033426  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003342d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033434  jz      short loc_1400333F8
0x140033436  mov     r9d, 50h ; 'P'
0x14003343c  jmp     short loc_1400333D4
0x14003343e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140033445  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003344c  jz      short loc_1400333F8
0x14003344e  mov     r9d, 4Fh ; 'O'
0x140033454  jmp     loc_1400333D4
0x140033459  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140033460  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033467  jz      short loc_1400333F8
0x140033469  mov     r9d, 4Eh ; 'N'
0x14003346f  jmp     loc_1400333D4
0x140033474  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003347b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033482  jz      loc_1400333F8
0x140033488  mov     r9d, 4Dh ; 'M'
0x14003348e  jmp     loc_1400333D4
0x140033493  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003349a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400334a1  jz      loc_1400333F8
0x1400334a7  mov     r9d, 4Ch ; 'L'
0x1400334ad  jmp     loc_1400333D4
0x1400334b2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400334b9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400334c0  jz      loc_1400333F8
0x1400334c6  mov     r9d, 4Bh ; 'K'
0x1400334cc  jmp     loc_1400333D4
0x1400334d1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400334d8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400334df  jz      loc_1400333F8
0x1400334e5  mov     r9d, 4Ah ; 'J'
0x1400334eb  jmp     loc_1400333D4
0x1400334f0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400334f7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400334fe  jz      loc_1400333F8
0x140033504  mov     r9d, 49h ; 'I'
0x14003350a  jmp     loc_1400333D4
0x14003350f  mov     edi, 0FEDh
0x140033514  mov     rbx, [rsp+38h+arg_0]
0x140033519  mov     eax, edi
0x14003351b  mov     rsi, [rsp+38h+arg_8]
0x140033520  add     rsp, 30h
0x140033524  pop     rdi
0x140033525  retn
```

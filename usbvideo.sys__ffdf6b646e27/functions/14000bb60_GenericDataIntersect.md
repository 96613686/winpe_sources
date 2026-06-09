# GenericDataIntersect

- ea: `0x14000bb60`
- end: `0x14000c1f8`
- name: `GenericDataIntersect`
- size: `1688`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int, _OWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000bb20`

## callees

- `0x140004bac`
- `0x14000bb60`
- `0x140040b40`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000bd11`
- `ntoskrnl!RtlCompareMemory` at `0x14000be84`
- `ntoskrnl!RtlCompareMemory` at `0x14000bfe3`
- `ntoskrnl!RtlCompareMemory` at `0x14000bd11`
- `ntoskrnl!RtlCompareMemory` at `0x14000be84`
- `ntoskrnl!RtlCompareMemory` at `0x14000bfe3`

## pseudocode

```c
__int64 __fastcall GenericDataIntersect(__int64 a1, unsigned int *a2, unsigned int a3, _OWORD *a4, unsigned int *a5)
{
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // ecx
  __int64 v17; // rcx
  __int64 v18; // rax
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_412e8667c1693d69367ca3076725fe7f_Traceguids);
  v9 = *(_QWORD *)(a1 + 48) - 0x11CEC35605589F80LL;
  if ( *(_QWORD *)(a1 + 48) == 0x11CEC35605589F80LL )
    v9 = *(_QWORD *)(a1 + 56) - 0x5A595500AA0001BFLL;
  if ( !v9 )
  {
    v14 = *((_QWORD *)a2 + 6) - 0x11CEC35605589F80LL;
    if ( *((_QWORD *)a2 + 6) == 0x11CEC35605589F80LL )
      v14 = *((_QWORD *)a2 + 7) - 0x5A595500AA0001BFLL;
    if ( !v14 && *(_DWORD *)a1 >= 0x128u )
    {
      if ( *(_DWORD *)(a1 + 64) == a2[16]
        && *(_DWORD *)(a1 + 68) == a2[17]
        && *(_DWORD *)(a1 + 72) == a2[18]
        && *(_DWORD *)(a1 + 76) == a2[19]
        && RtlCompareMemory((const void *)(a1 + 80), a2 + 20, 0x80u) == 128
        && *(_DWORD *)(a1 + 260) == a2[65]
        && *(_DWORD *)(a1 + 264) == a2[66] )
      {
        v15 = *(_DWORD *)(a1 + 256);
        if ( v15 + 48 >= v15 && v15 + 256 >= v15 + 48 && v15 + 256 <= *(_DWORD *)a1 )
        {
          v16 = v15 + 112;
          if ( v15 + 112 >= 0x40 )
          {
            if ( a3 )
            {
              if ( a3 >= v16 )
              {
                *a5 = v16;
                *a4 = *(_OWORD *)a2;
                a4[1] = *((_OWORD *)a2 + 1);
                a4[2] = *((_OWORD *)a2 + 2);
                a4[3] = *((_OWORD *)a2 + 3);
                *(_DWORD *)a4 = v16;
                memmove(a4 + 4, (const void *)(a1 + 208), (unsigned int)(*(_DWORD *)(a1 + 256) + 48));
                v17 = *((_QWORD *)a2 + 24);
                if ( *((_QWORD *)a4 + 13) > v17 )
                {
                  *((_QWORD *)a4 + 13) = v17;
                  *((_DWORD *)a4 + 24) = a2[50];
                }
                else
                {
                  v17 = *((_QWORD *)a4 + 13);
                }
                v18 = *((_QWORD *)a2 + 23);
                if ( v17 < v18 )
                {
                  *((_QWORD *)a4 + 13) = v18;
                  *((_DWORD *)a4 + 24) = a2[51];
                }
                v19 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
                  return 0;
                v20 = 21;
                goto LABEL_86;
              }
              return 3221225507LL;
            }
            goto LABEL_88;
          }
        }
        return 3221225485LL;
      }
      return 3221226098LL;
    }
  }
  v10 = *(_QWORD *)(a1 + 48) - 0x11D0EB0AF72A76A0LL;
  if ( *(_QWORD *)(a1 + 48) == 0x11D0EB0AF72A76A0LL )
    v10 = *(_QWORD *)(a1 + 56) + 0x45E9333FFFFF1B54LL;
  if ( !v10 )
  {
    v21 = *((_QWORD *)a2 + 6) - 0x11D0EB0AF72A76A0LL;
    if ( *((_QWORD *)a2 + 6) == 0x11D0EB0AF72A76A0LL )
      v21 = *((_QWORD *)a2 + 7) + 0x45E9333FFFFF1B54LL;
    if ( !v21 && *(_DWORD *)a1 >= 0x140u )
    {
      if ( *(_DWORD *)(a1 + 64) != a2[16]
        || *(_DWORD *)(a1 + 68) != a2[17]
        || *(_DWORD *)(a1 + 72) != a2[18]
        || *(_DWORD *)(a1 + 76) != a2[19]
        || RtlCompareMemory((const void *)(a1 + 80), a2 + 20, 0x80u) != 128
        || *(_DWORD *)(a1 + 284) != a2[71]
        || *(_DWORD *)(a1 + 288) != a2[72] )
      {
        return 3221226098LL;
      }
      v22 = *(_DWORD *)(a1 + 280);
      if ( v22 + 72 < v22 )
        return 3221225485LL;
      if ( v22 + 280 < v22 + 72 )
        return 3221225485LL;
      if ( v22 + 280 > *(_DWORD *)a1 )
        return 3221225485LL;
      v16 = v22 + 136;
      if ( v22 + 136 < 0x40 )
        return 3221225485LL;
      if ( !a3 )
      {
LABEL_88:
        *a5 = v16;
        return 2147483653LL;
      }
      if ( a3 >= v16 )
      {
        *a5 = v16;
        *a4 = *(_OWORD *)a2;
        a4[1] = *((_OWORD *)a2 + 1);
        a4[2] = *((_OWORD *)a2 + 2);
        a4[3] = *((_OWORD *)a2 + 3);
        *(_DWORD *)a4 = v16;
        memmove(a4 + 4, (const void *)(a1 + 208), (unsigned int)(*(_DWORD *)(a1 + 280) + 72));
        v23 = *((_QWORD *)a2 + 24);
        if ( *((_QWORD *)a4 + 13) > v23 )
        {
          *((_QWORD *)a4 + 13) = v23;
          *((_DWORD *)a4 + 24) = a2[50];
        }
        else
        {
          v23 = *((_QWORD *)a4 + 13);
        }
        v24 = *((_QWORD *)a2 + 23);
        if ( v23 < v24 )
        {
          *((_QWORD *)a4 + 13) = v24;
          *((_DWORD *)a4 + 24) = a2[51];
        }
        return 0;
      }
      return 3221225507LL;
    }
  }
  v11 = *(_QWORD *)(a1 + 48) - 0x11CEC35605589F84LL;
  if ( *(_QWORD *)(a1 + 48) == 0x11CEC35605589F84LL )
    v11 = *(_QWORD *)(a1 + 56) - 0x5A595500AA0001BFLL;
  if ( v11 )
    goto LABEL_11;
  v26 = *((_QWORD *)a2 + 6) - 0x11CEC35605589F84LL;
  if ( *((_QWORD *)a2 + 6) == 0x11CEC35605589F84LL )
    v26 = *((_QWORD *)a2 + 7) - 0x5A595500AA0001BFLL;
  if ( v26 || *(_DWORD *)a1 < 0x60u )
  {
LABEL_11:
    v12 = *(_QWORD *)(a1 + 48) - 0x424866292017BE05LL;
    if ( *(_QWORD *)(a1 + 48) == 0x424866292017BE05LL )
      v12 = *(_QWORD *)(a1 + 56) + 0x636443B8E5811256LL;
    if ( !v12 )
    {
      v25 = *((_QWORD *)a2 + 6) - 0x424866292017BE05LL;
      if ( *((_QWORD *)a2 + 6) == 0x424866292017BE05LL )
        v25 = *((_QWORD *)a2 + 7) + 0x636443B8E5811256LL;
      if ( !v25
        && *(_DWORD *)a1 >= 0x128u
        && *(_DWORD *)(a1 + 64) == a2[16]
        && *(_DWORD *)(a1 + 68) == a2[17]
        && *(_DWORD *)(a1 + 72) == a2[18]
        && *(_DWORD *)(a1 + 76) == a2[19]
        && RtlCompareMemory((const void *)(a1 + 80), a2 + 20, 0x80u) == 128 )
      {
        *a5 = 148;
        if ( a3 )
        {
          if ( a3 >= 0x94 )
          {
            *a4 = *(_OWORD *)a2;
            a4[1] = *((_OWORD *)a2 + 1);
            a4[2] = *((_OWORD *)a2 + 2);
            a4[3] = *((_OWORD *)a2 + 3);
            *(_DWORD *)a4 = 148;
            a4[4] = *(_OWORD *)(a1 + 208);
            a4[5] = *(_OWORD *)(a1 + 224);
            a4[6] = *(_OWORD *)(a1 + 240);
            a4[7] = *(_OWORD *)(a1 + 256);
            a4[8] = *(_OWORD *)(a1 + 272);
            *((_DWORD *)a4 + 36) = *(_DWORD *)(a1 + 288);
            return 0;
          }
          return 3221225507LL;
        }
        return 2147483653LL;
      }
    }
    return 3221226098LL;
  }
  if ( a3 )
  {
    if ( a3 >= 0x60 )
    {
      if ( *(_DWORD *)(a1 + 8) == a2[2] )
      {
        if ( *a2 == 96 )
        {
          *a5 = 96;
          memmove(a4, a2, *a2);
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
            return 0;
          v20 = 23;
LABEL_86:
          WPP_SF_(v19->AttachedDevice, v20, WPP_412e8667c1693d69367ca3076725fe7f_Traceguids);
          return 0;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_412e8667c1693d69367ca3076725fe7f_Traceguids);
      }
      return 3221226098LL;
    }
    return 3221225507LL;
  }
  *a5 = 96;
  return 2147483653LL;
}

```

## disassembly

```asm
0x14000bb60  push    rbp
0x14000bb62  push    rbx
0x14000bb63  push    rsi
0x14000bb64  push    rdi
0x14000bb65  push    r14
0x14000bb67  push    r15
0x14000bb69  mov     rbp, rsp
0x14000bb6c  sub     rsp, 68h
0x14000bb70  mov     r14, r9
0x14000bb73  mov     dword ptr [rbp+var_48], 5589F80h
0x14000bb7a  mov     esi, r8d
0x14000bb7d  mov     dword ptr [rbp+var_48+4], 11CEC356h
0x14000bb84  mov     rdi, rdx
0x14000bb87  mov     dword ptr [rbp+var_40], 0AA0001BFh
0x14000bb8e  mov     rbx, rcx
0x14000bb91  mov     dword ptr [rbp+var_40+4], 5A595500h
0x14000bb98  mov     dword ptr [rbp+var_28], 5589F84h
0x14000bb9f  mov     dword ptr [rbp+var_28+4], 11CEC356h
0x14000bba6  mov     dword ptr [rbp+var_20], 0AA0001BFh
0x14000bbad  mov     dword ptr [rbp+var_20+4], 5A595500h
0x14000bbb4  mov     dword ptr [rbp+var_38], 0F72A76A0h
0x14000bbbb  mov     dword ptr [rbp+var_38+4], 11D0EB0Ah
0x14000bbc2  mov     dword ptr [rbp+var_30], 0E4ACh
0x14000bbc9  mov     dword ptr [rbp+var_30+4], 0BA16CCC0h
0x14000bbd0  mov     dword ptr [rbp+var_18], 2017BE05h
0x14000bbd7  mov     dword ptr [rbp+var_18+4], 42486629h
0x14000bbde  mov     dword ptr [rbp+var_10], 1A7EEDAAh
0x14000bbe5  mov     dword ptr [rbp+var_10+4], 9C9BBC47h
0x14000bbec  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bbf3  lea     r15, WPP_GLOBAL_Control
0x14000bbfa  cmp     rcx, r15
0x14000bbfd  jnz     loc_14000BC9A
0x14000bc03  mov     rax, [rbx+30h]
0x14000bc07  mov     rdx, [rbp+var_48]
0x14000bc0b  mov     rcx, [rbp+var_40]
0x14000bc0f  sub     rax, rdx
0x14000bc12  jnz     short loc_14000BC1B
0x14000bc14  mov     rax, [rbx+38h]
0x14000bc18  sub     rax, rcx
0x14000bc1b  test    rax, rax
0x14000bc1e  jz      loc_14000BCBE
0x14000bc24  mov     rax, [rbx+30h]
0x14000bc28  mov     rdx, [rbp+var_38]
0x14000bc2c  mov     rcx, [rbp+var_30]
0x14000bc30  sub     rax, rdx
0x14000bc33  jnz     short loc_14000BC3C
0x14000bc35  mov     rax, [rbx+38h]
0x14000bc39  sub     rax, rcx
0x14000bc3c  test    rax, rax
0x14000bc3f  jz      loc_14000BE21
0x14000bc45  mov     rax, [rbx+30h]
0x14000bc49  mov     rdx, [rbp+var_28]
0x14000bc4d  mov     rcx, [rbp+var_20]
0x14000bc51  sub     rax, rdx
0x14000bc54  jnz     short loc_14000BC5D
0x14000bc56  mov     rax, [rbx+38h]
0x14000bc5a  sub     rax, rcx
0x14000bc5d  test    rax, rax
0x14000bc60  jz      loc_14000C095
0x14000bc66  mov     rax, [rbx+30h]
0x14000bc6a  mov     rdx, [rbp+var_18]
0x14000bc6e  mov     rcx, [rbp+var_10]
0x14000bc72  sub     rax, rdx
0x14000bc75  jnz     short loc_14000BC7E
0x14000bc77  mov     rax, [rbx+38h]
0x14000bc7b  sub     rax, rcx
0x14000bc7e  test    rax, rax
0x14000bc81  jz      loc_14000BF80
0x14000bc87  mov     eax, 0C0000272h
0x14000bc8c  add     rsp, 68h
0x14000bc90  pop     r15
0x14000bc92  pop     r14
0x14000bc94  pop     rdi
0x14000bc95  pop     rsi
0x14000bc96  pop     rbx
0x14000bc97  pop     rbp
0x14000bc98  retn
0x14000bc9a  cmp     byte ptr [rcx+29h], 5
0x14000bc9e  jb      loc_14000BC03
0x14000bca4  mov     rcx, [rcx+18h]
0x14000bca8  lea     r8, WPP_412e8667c1693d69367ca3076725fe7f_Traceguids
0x14000bcaf  mov     edx, 14h
0x14000bcb4  call    WPP_SF_
0x14000bcb9  jmp     loc_14000BC03
0x14000bcbe  mov     rax, [rdi+30h]
0x14000bcc2  sub     rax, rdx
0x14000bcc5  jnz     short loc_14000BCCE
0x14000bcc7  mov     rax, [rdi+38h]
0x14000bccb  sub     rax, rcx
0x14000bcce  test    rax, rax
0x14000bcd1  jnz     loc_14000BC24
0x14000bcd7  cmp     dword ptr [rbx], 128h
0x14000bcdd  jb      loc_14000BC24
0x14000bce3  mov     eax, [rdi+40h]
0x14000bce6  cmp     [rbx+40h], eax
0x14000bce9  jnz     short loc_14000BC87
0x14000bceb  mov     eax, [rdi+44h]
0x14000bcee  cmp     [rbx+44h], eax
0x14000bcf1  jnz     short loc_14000BC87
0x14000bcf3  mov     eax, [rdi+48h]
0x14000bcf6  cmp     [rbx+48h], eax
0x14000bcf9  jnz     short loc_14000BC87
0x14000bcfb  mov     eax, [rdi+4Ch]
0x14000bcfe  cmp     [rbx+4Ch], eax
0x14000bd01  jnz     short loc_14000BC87
0x14000bd03  lea     rdx, [rdi+50h]; Source2
0x14000bd07  mov     r8d, 80h; Length
0x14000bd0d  lea     rcx, [rbx+50h]; Source1
0x14000bd11  call    cs:__imp_RtlCompareMemory
0x14000bd18  nop     dword ptr [rax+rax+00h]
0x14000bd1d  cmp     rax, 80h
0x14000bd23  jnz     loc_14000BC87
0x14000bd29  mov     eax, [rdi+104h]
0x14000bd2f  cmp     [rbx+104h], eax
0x14000bd35  jnz     loc_14000BC87
0x14000bd3b  mov     eax, [rdi+108h]
0x14000bd41  cmp     [rbx+108h], eax
0x14000bd47  jnz     loc_14000BC87
0x14000bd4d  mov     eax, [rbx+100h]
0x14000bd53  lea     ecx, [rax+30h]
0x14000bd56  cmp     ecx, eax
0x14000bd58  jb      loc_14000C151
0x14000bd5e  lea     eax, [rcx+0D0h]
0x14000bd64  cmp     eax, ecx
0x14000bd66  jb      loc_14000C151
0x14000bd6c  cmp     eax, [rbx]
0x14000bd6e  ja      loc_14000C151
0x14000bd74  add     ecx, 40h ; '@'
0x14000bd77  cmp     ecx, 40h ; '@'
0x14000bd7a  jb      loc_14000C151
0x14000bd80  test    esi, esi
0x14000bd82  jz      loc_14000C138
0x14000bd88  cmp     esi, ecx
0x14000bd8a  jb      loc_14000C125
0x14000bd90  mov     rax, [rbp+arg_20]
0x14000bd94  lea     rdx, [rbx+0D0h]; Src
0x14000bd9b  mov     [rax], ecx
0x14000bd9d  movups  xmm0, xmmword ptr [rdi]
0x14000bda0  movups  xmmword ptr [r14], xmm0
0x14000bda4  movups  xmm1, xmmword ptr [rdi+10h]
0x14000bda8  movups  xmmword ptr [r14+10h], xmm1
0x14000bdad  movups  xmm0, xmmword ptr [rdi+20h]
0x14000bdb1  movups  xmmword ptr [r14+20h], xmm0
0x14000bdb6  movups  xmm1, xmmword ptr [rdi+30h]
0x14000bdba  movups  xmmword ptr [r14+30h], xmm1
0x14000bdbf  mov     [r14], ecx
0x14000bdc2  lea     rcx, [r14+40h]; void *
0x14000bdc6  mov     r8d, [rbx+100h]
0x14000bdcd  add     r8d, 30h ; '0'; Size
0x14000bdd1  call    memmove
0x14000bdd6  mov     rcx, [rdi+0C0h]
0x14000bddd  mov     rax, [r14+68h]
0x14000bde1  cmp     rax, rcx
0x14000bde4  jg      loc_14000C164
0x14000bdea  mov     rcx, rax
0x14000bded  mov     rax, [rdi+0B8h]
0x14000bdf4  cmp     rcx, rax
0x14000bdf7  jl      loc_14000C177
0x14000bdfd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000be04  cmp     rcx, r15
0x14000be07  jz      loc_14000BF70
0x14000be0d  cmp     byte ptr [rcx+29h], 5
0x14000be11  jb      loc_14000BF70
0x14000be17  mov     edx, 15h
0x14000be1c  jmp     loc_14000C110
0x14000be21  mov     rax, [rdi+30h]
0x14000be25  sub     rax, rdx
0x14000be28  jnz     short loc_14000BE31
0x14000be2a  mov     rax, [rdi+38h]
0x14000be2e  sub     rax, rcx
0x14000be31  test    rax, rax
0x14000be34  jnz     loc_14000BC45
0x14000be3a  cmp     dword ptr [rbx], 140h
0x14000be40  jb      loc_14000BC45
0x14000be46  mov     eax, [rdi+40h]
0x14000be49  cmp     [rbx+40h], eax
0x14000be4c  jnz     loc_14000BC87
0x14000be52  mov     eax, [rdi+44h]
0x14000be55  cmp     [rbx+44h], eax
0x14000be58  jnz     loc_14000BC87
0x14000be5e  mov     eax, [rdi+48h]
0x14000be61  cmp     [rbx+48h], eax
0x14000be64  jnz     loc_14000BC87
0x14000be6a  mov     eax, [rdi+4Ch]
0x14000be6d  cmp     [rbx+4Ch], eax
0x14000be70  jnz     loc_14000BC87
0x14000be76  lea     rdx, [rdi+50h]; Source2
0x14000be7a  mov     r8d, 80h; Length
0x14000be80  lea     rcx, [rbx+50h]; Source1
0x14000be84  call    cs:__imp_RtlCompareMemory
0x14000be8b  nop     dword ptr [rax+rax+00h]
0x14000be90  cmp     rax, 80h
0x14000be96  jnz     loc_14000BC87
0x14000be9c  mov     eax, [rdi+11Ch]
0x14000bea2  cmp     [rbx+11Ch], eax
0x14000bea8  jnz     loc_14000BC87
0x14000beae  mov     eax, [rdi+120h]
0x14000beb4  cmp     [rbx+120h], eax
0x14000beba  jnz     loc_14000BC87
0x14000bec0  mov     eax, [rbx+118h]
0x14000bec6  lea     ecx, [rax+48h]
0x14000bec9  cmp     ecx, eax
0x14000becb  jb      loc_14000C151
0x14000bed1  lea     eax, [rcx+0D0h]
0x14000bed7  cmp     eax, ecx
0x14000bed9  jb      loc_14000C151
0x14000bedf  cmp     eax, [rbx]
0x14000bee1  ja      loc_14000C151
0x14000bee7  add     ecx, 40h ; '@'
0x14000beea  cmp     ecx, 40h ; '@'
0x14000beed  jb      loc_14000C151
0x14000bef3  test    esi, esi
0x14000bef5  jz      loc_14000C138
0x14000befb  cmp     esi, ecx
0x14000befd  jb      loc_14000C125
0x14000bf03  mov     rax, [rbp+arg_20]
0x14000bf07  lea     rdx, [rbx+0D0h]; Src
0x14000bf0e  mov     [rax], ecx
0x14000bf10  movups  xmm0, xmmword ptr [rdi]
0x14000bf13  movups  xmmword ptr [r14], xmm0
0x14000bf17  movups  xmm1, xmmword ptr [rdi+10h]
0x14000bf1b  movups  xmmword ptr [r14+10h], xmm1
0x14000bf20  movups  xmm0, xmmword ptr [rdi+20h]
0x14000bf24  movups  xmmword ptr [r14+20h], xmm0
0x14000bf29  movups  xmm1, xmmword ptr [rdi+30h]
0x14000bf2d  movups  xmmword ptr [r14+30h], xmm1
0x14000bf32  mov     [r14], ecx
0x14000bf35  lea     rcx, [r14+40h]; void *
0x14000bf39  mov     r8d, [rbx+118h]
0x14000bf40  add     r8d, 48h ; 'H'; Size
0x14000bf44  call    memmove
0x14000bf49  mov     rcx, [rdi+0C0h]
0x14000bf50  mov     rax, [r14+68h]
0x14000bf54  cmp     rax, rcx
0x14000bf57  jg      loc_14000C18A
0x14000bf5d  mov     rcx, rax
0x14000bf60  mov     rax, [rdi+0B8h]
0x14000bf67  cmp     rcx, rax
0x14000bf6a  jl      loc_14000C19D
0x14000bf70  xor     eax, eax
0x14000bf72  add     rsp, 68h
0x14000bf76  pop     r15
0x14000bf78  pop     r14
0x14000bf7a  pop     rdi
0x14000bf7b  pop     rsi
0x14000bf7c  pop     rbx
0x14000bf7d  pop     rbp
0x14000bf7e  retn
0x14000bf80  mov     rax, [rdi+30h]
0x14000bf84  sub     rax, rdx
0x14000bf87  jnz     short loc_14000BF90
0x14000bf89  mov     rax, [rdi+38h]
0x14000bf8d  sub     rax, rcx
0x14000bf90  test    rax, rax
0x14000bf93  jnz     loc_14000BC87
0x14000bf99  cmp     dword ptr [rbx], 128h
0x14000bf9f  jb      loc_14000BC87
0x14000bfa5  mov     eax, [rdi+40h]
0x14000bfa8  cmp     [rbx+40h], eax
0x14000bfab  jnz     loc_14000BC87
0x14000bfb1  mov     eax, [rdi+44h]
0x14000bfb4  cmp     [rbx+44h], eax
0x14000bfb7  jnz     loc_14000BC87
0x14000bfbd  mov     eax, [rdi+48h]
0x14000bfc0  cmp     [rbx+48h], eax
0x14000bfc3  jnz     loc_14000BC87
0x14000bfc9  mov     eax, [rdi+4Ch]
0x14000bfcc  cmp     [rbx+4Ch], eax
0x14000bfcf  jnz     loc_14000BC87
0x14000bfd5  lea     rdx, [rdi+50h]; Source2
0x14000bfd9  mov     r8d, 80h; Length
0x14000bfdf  lea     rcx, [rbx+50h]; Source1
0x14000bfe3  call    cs:__imp_RtlCompareMemory
0x14000bfea  nop     dword ptr [rax+rax+00h]
0x14000bfef  cmp     rax, 80h
0x14000bff5  jnz     loc_14000BC87
0x14000bffb  mov     rax, [rbp+arg_20]
0x14000bfff  mov     dword ptr [rax], 94h
0x14000c005  test    esi, esi
0x14000c007  jz      loc_14000C13E
0x14000c00d  cmp     esi, 94h
0x14000c013  jb      loc_14000C125
0x14000c019  movups  xmm0, xmmword ptr [rdi]
0x14000c01c  movups  xmmword ptr [r14], xmm0
0x14000c020  movups  xmm1, xmmword ptr [rdi+10h]
0x14000c024  movups  xmmword ptr [r14+10h], xmm1
0x14000c029  movups  xmm0, xmmword ptr [rdi+20h]
0x14000c02d  movups  xmmword ptr [r14+20h], xmm0
0x14000c032  movups  xmm1, xmmword ptr [rdi+30h]
0x14000c036  movups  xmmword ptr [r14+30h], xmm1
0x14000c03b  mov     dword ptr [r14], 94h
0x14000c042  movups  xmm0, xmmword ptr [rbx+0D0h]
0x14000c049  movups  xmmword ptr [r14+40h], xmm0
0x14000c04e  movups  xmm1, xmmword ptr [rbx+0E0h]
0x14000c055  movups  xmmword ptr [r14+50h], xmm1
0x14000c05a  movups  xmm0, xmmword ptr [rbx+0F0h]
0x14000c061  movups  xmmword ptr [r14+60h], xmm0
0x14000c066  movups  xmm1, xmmword ptr [rbx+100h]
0x14000c06d  movups  xmmword ptr [r14+70h], xmm1
0x14000c072  movups  xmm0, xmmword ptr [rbx+110h]
  ... truncated ...
```

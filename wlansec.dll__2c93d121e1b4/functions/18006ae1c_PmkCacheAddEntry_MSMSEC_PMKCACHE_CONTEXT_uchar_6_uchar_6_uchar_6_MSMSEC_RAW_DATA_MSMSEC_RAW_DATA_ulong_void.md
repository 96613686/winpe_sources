# PmkCacheAddEntry(MSMSEC_PMKCACHE_CONTEXT *,uchar (*)[6],uchar (*)[6],uchar (*)[6],MSMSEC_RAW_DATA *,MSMSEC_RAW_DATA *,ulong,void *)

- ea: `0x18006ae1c`
- end: `0x18006b0a5`
- name: `?PmkCacheAddEntry@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@PEAY05E11PEAUMSMSEC_RAW_DATA@@2KPEAX@Z`
- size: `649`
- prototype: `unsigned int __fastcall(struct MSMSEC_PMKCACHE_CONTEXT *, unsigned __int8 (*)[6], unsigned __int8 (*)[6], unsigned __int8 (*)[6], struct MSMSEC_RAW_DATA *, struct MSMSEC_RAW_DATA *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800695d0`

## callees

- `0x18000892c`
- `0x18000895c`
- `0x180008998`
- `0x18002ec3c`
- `0x18006a91c`
- `0x18006ae1c`

## import_xrefs

- `OneX!OneXCompareAuthParams` at `0x18006af53`
- `OneX!OneXCompareAuthParams` at `0x18006af53`

## pseudocode

```c
__int64 __fastcall PmkCacheAddEntry(
        struct MSMSEC_PMKCACHE_CONTEXT *a1,
        unsigned __int8 (*a2)[6],
        unsigned __int8 (*a3)[6],
        unsigned __int8 (*a4)[6],
        unsigned __int8 **a5,
        struct MSMSEC_RAW_DATA *a6,
        unsigned int a7,
        void *a8)
{
  PVOID *v12; // r10
  unsigned int v13; // ebx
  __int64 v14; // rdx
  int v15; // ecx
  unsigned int PMKIDFromProtectedPMK; // eax
  __int64 v17; // rdx
  struct MSMSEC_RAW_DATA *v18; // rsi
  unsigned __int8 v20[16]; // [rsp+40h] [rbp-38h] BYREF
  int v21; // [rsp+80h] [rbp+8h] BYREF

  *(_OWORD *)v20 = 0;
  v21 = 1;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 173, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)a1 )
  {
    if ( (unsigned int)IsPMKCacheValid(a1) )
    {
      v15 = *(_DWORD *)a4 - *((_DWORD *)a1 + 14);
      if ( *(_DWORD *)a4 == *((_DWORD *)a1 + 14) )
        v15 = *(unsigned __int16 *)&(*a4)[4] - *((unsigned __int16 *)a1 + 30);
      if ( v15 )
      {
        PMKIDFromProtectedPMK = OneXCompareAuthParams(
                                  1,
                                  *((unsigned int *)a1 + 48),
                                  *((_QWORD *)a1 + 25),
                                  a7,
                                  a8,
                                  &v21,
                                  0);
        v13 = PMKIDFromProtectedPMK;
        if ( PMKIDFromProtectedPMK )
        {
          v12 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v13;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_37;
          v17 = 177;
        }
        else
        {
          if ( v21 )
          {
            v13 = 1168;
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v13;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              goto LABEL_37;
            v14 = 178;
            goto LABEL_8;
          }
          v18 = (struct MSMSEC_RAW_DATA *)a5;
          PMKIDFromProtectedPMK = GeneratePMKIDFromProtectedPMK(
                                    a1,
                                    a2,
                                    a3,
                                    a5[1],
                                    *(_DWORD *)a5,
                                    (unsigned __int8 (*)[16])v20);
          v13 = PMKIDFromProtectedPMK;
          if ( PMKIDFromProtectedPMK )
          {
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v13;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              goto LABEL_37;
            v17 = 179;
          }
          else
          {
            PMKIDFromProtectedPMK = PmkCacheAddEntryInt(a1, a4, v18, a6, (unsigned __int8 (*)[16])v20);
            v13 = PMKIDFromProtectedPMK;
            if ( !PMKIDFromProtectedPMK )
              goto LABEL_36;
            v12 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              return v13;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              goto LABEL_37;
            v17 = 180;
          }
        }
        WPP_SF_d(v12[7], v17, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, PMKIDFromProtectedPMK);
        goto LABEL_36;
      }
      v13 = 87;
      if ( v12 == &WPP_GLOBAL_Control )
        return v13;
      if ( (*((_BYTE *)v12 + 68) & 1) == 0 )
        goto LABEL_37;
      v14 = 176;
    }
    else
    {
      v13 = 5023;
      if ( v12 == &WPP_GLOBAL_Control )
        return v13;
      if ( (*((_BYTE *)v12 + 68) & 1) == 0 )
        goto LABEL_37;
      v14 = 175;
    }
LABEL_8:
    WPP_SF_(v12[7], v14, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids);
LABEL_36:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_37;
  }
  v13 = 0;
  if ( v12 == &WPP_GLOBAL_Control )
    return v13;
  if ( (*((_BYTE *)v12 + 68) & 2) != 0 )
  {
    v14 = 174;
    goto LABEL_8;
  }
LABEL_37:
  if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 17) & 0x100) != 0 )
    WPP_SF_d(v12[7], 181, &WPP_33279517f8f53e554228e3ed86a1217c_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x18006ae1c  mov     rax, rsp
0x18006ae1f  mov     [rax+10h], rbx
0x18006ae23  mov     [rax+18h], rbp
0x18006ae27  push    rsi
0x18006ae28  push    rdi
0x18006ae29  push    r12
0x18006ae2b  push    r14
0x18006ae2d  push    r15
0x18006ae2f  sub     rsp, 50h
0x18006ae33  xorps   xmm0, xmm0
0x18006ae36  mov     esi, 1
0x18006ae3b  movups  xmmword ptr [rax-38h], xmm0
0x18006ae3f  mov     [rax+8], esi
0x18006ae42  mov     r14, r9
0x18006ae45  mov     rbp, r8
0x18006ae48  mov     r15, rdx
0x18006ae4b  mov     rdi, rcx
0x18006ae4e  mov     r10, cs:WPP_GLOBAL_Control
0x18006ae55  lea     r12, WPP_GLOBAL_Control
0x18006ae5c  cmp     r10, r12
0x18006ae5f  jz      short loc_18006AE87
0x18006ae61  test    dword ptr [r10+44h], 100h
0x18006ae69  jz      short loc_18006AE87
0x18006ae6b  mov     rcx, [r10+38h]
0x18006ae6f  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18006ae76  mov     edx, 0ADh
0x18006ae7b  call    WPP_SF_
0x18006ae80  mov     r10, cs:WPP_GLOBAL_Control
0x18006ae87  cmp     dword ptr [rdi], 0
0x18006ae8a  jnz     short loc_18006AEBC
0x18006ae8c  xor     ebx, ebx
0x18006ae8e  cmp     r10, r12
0x18006ae91  jz      loc_18006B089
0x18006ae97  test    byte ptr [r10+44h], 2
0x18006ae9c  jz      loc_18006B062
0x18006aea2  mov     edx, 0AEh
0x18006aea7  mov     rcx, [r10+38h]
0x18006aeab  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18006aeb2  call    WPP_SF_
0x18006aeb7  jmp     loc_18006B05B
0x18006aebc  mov     rcx, rdi; struct MSMSEC_PMKCACHE_CONTEXT *
0x18006aebf  call    ?IsPMKCacheValid@@YAHPEAUMSMSEC_PMKCACHE_CONTEXT@@@Z; IsPMKCacheValid(MSMSEC_PMKCACHE_CONTEXT *)
0x18006aec4  test    eax, eax
0x18006aec6  jnz     short loc_18006AEE7
0x18006aec8  mov     ebx, 139Fh
0x18006aecd  cmp     r10, r12
0x18006aed0  jz      loc_18006B089
0x18006aed6  test    [r10+44h], sil
0x18006aeda  jz      loc_18006B062
0x18006aee0  mov     edx, 0AFh
0x18006aee5  jmp     short loc_18006AEA7
0x18006aee7  mov     ecx, [r14]
0x18006aeea  sub     ecx, [rdi+38h]
0x18006aeed  jnz     short loc_18006AEFA
0x18006aeef  movzx   ecx, word ptr [r14+4]
0x18006aef4  movzx   eax, word ptr [rdi+3Ch]
0x18006aef8  sub     ecx, eax
0x18006aefa  test    ecx, ecx
0x18006aefc  jnz     short loc_18006AF19
0x18006aefe  lea     ebx, [rcx+57h]
0x18006af01  cmp     r10, r12
0x18006af04  jz      loc_18006B089
0x18006af0a  test    [r10+44h], sil
0x18006af0e  jz      loc_18006B062
0x18006af14  lea     edx, [rbx+59h]
0x18006af17  jmp     short loc_18006AEA7
0x18006af19  mov     r9d, [rsp+78h+arg_30]
0x18006af21  lea     rax, [rsp+78h+arg_0]
0x18006af29  mov     r8, [rdi+0C8h]
0x18006af30  mov     ecx, esi
0x18006af32  mov     edx, [rdi+0C0h]
0x18006af38  mov     [rsp+78h+var_48], 0
0x18006af41  mov     [rsp+78h+var_50], rax
0x18006af46  mov     rax, [rsp+78h+arg_38]
0x18006af4e  mov     [rsp+78h+var_58], rax
0x18006af53  call    cs:__imp_OneXCompareAuthParams
0x18006af5a  nop     dword ptr [rax+rax+00h]
0x18006af5f  mov     ebx, eax
0x18006af61  test    eax, eax
0x18006af63  jz      short loc_18006AF89
0x18006af65  mov     r10, cs:WPP_GLOBAL_Control
0x18006af6c  cmp     r10, r12
0x18006af6f  jz      loc_18006B089
0x18006af75  test    [r10+44h], sil
0x18006af79  jz      loc_18006B062
0x18006af7f  mov     edx, 0B1h
0x18006af84  jmp     loc_18006B048
0x18006af89  cmp     [rsp+78h+arg_0], 0
0x18006af91  jz      short loc_18006AFBC
0x18006af93  mov     ebx, 490h
0x18006af98  mov     r10, cs:WPP_GLOBAL_Control
0x18006af9f  cmp     r10, r12
0x18006afa2  jz      loc_18006B089
0x18006afa8  test    [r10+44h], sil
0x18006afac  jz      loc_18006B062
0x18006afb2  mov     edx, 0B2h
0x18006afb7  jmp     loc_18006AEA7
0x18006afbc  mov     rsi, [rsp+78h+arg_20]
0x18006afc4  lea     rax, [rsp+78h+var_38]
0x18006afc9  mov     [rsp+78h+var_50], rax; unsigned __int8 (*)[16]
0x18006afce  mov     r8, rbp; unsigned __int8 (*)[6]
0x18006afd1  mov     rdx, r15; unsigned __int8 (*)[6]
0x18006afd4  mov     rcx, rdi; struct MSMSEC_PMKCACHE_CONTEXT *
0x18006afd7  mov     eax, [rsi]
0x18006afd9  mov     r9, [rsi+8]; unsigned __int8 *
0x18006afdd  mov     dword ptr [rsp+78h+var_58], eax; unsigned int
0x18006afe1  call    ?GeneratePMKIDFromProtectedPMK@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@PEAY05E1PEAEKPEAY0BA@E@Z; GeneratePMKIDFromProtectedPMK(MSMSEC_PMKCACHE_CONTEXT *,uchar (*)[6],uchar (*)[6],uchar *,ulong,uchar (*)[16])
0x18006afe6  mov     ebx, eax
0x18006afe8  test    eax, eax
0x18006afea  jz      short loc_18006B00A
0x18006afec  mov     r10, cs:WPP_GLOBAL_Control
0x18006aff3  cmp     r10, r12
0x18006aff6  jz      loc_18006B089
0x18006affc  test    byte ptr [r10+44h], 1
0x18006b001  jz      short loc_18006B062
0x18006b003  mov     edx, 0B3h
0x18006b008  jmp     short loc_18006B048
0x18006b00a  mov     r9, [rsp+78h+arg_28]; struct MSMSEC_RAW_DATA *
0x18006b012  lea     rax, [rsp+78h+var_38]
0x18006b017  mov     r8, rsi; struct MSMSEC_RAW_DATA *
0x18006b01a  mov     [rsp+78h+var_58], rax; unsigned __int8 (*)[16]
0x18006b01f  mov     rdx, r14; unsigned __int8 (*)[6]
0x18006b022  mov     rcx, rdi; struct MSMSEC_PMKCACHE_CONTEXT *
0x18006b025  call    ?PmkCacheAddEntryInt@@YAKPEAUMSMSEC_PMKCACHE_CONTEXT@@PEAY05EPEAUMSMSEC_RAW_DATA@@2PEAY0BA@E@Z; PmkCacheAddEntryInt(MSMSEC_PMKCACHE_CONTEXT *,uchar (*)[6],MSMSEC_RAW_DATA *,MSMSEC_RAW_DATA *,uchar (*)[16])
0x18006b02a  mov     ebx, eax
0x18006b02c  test    eax, eax
0x18006b02e  jz      short loc_18006B05B
0x18006b030  mov     r10, cs:WPP_GLOBAL_Control
0x18006b037  cmp     r10, r12
0x18006b03a  jz      short loc_18006B089
0x18006b03c  test    byte ptr [r10+44h], 1
0x18006b041  jz      short loc_18006B062
0x18006b043  mov     edx, 0B4h
0x18006b048  mov     rcx, [r10+38h]
0x18006b04c  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18006b053  mov     r9d, eax
0x18006b056  call    WPP_SF_d
0x18006b05b  mov     r10, cs:WPP_GLOBAL_Control
0x18006b062  cmp     r10, r12
0x18006b065  jz      short loc_18006B089
0x18006b067  test    dword ptr [r10+44h], 100h
0x18006b06f  jz      short loc_18006B089
0x18006b071  mov     rcx, [r10+38h]
0x18006b075  lea     r8, WPP_33279517f8f53e554228e3ed86a1217c_Traceguids
0x18006b07c  mov     edx, 0B5h
0x18006b081  mov     r9d, ebx
0x18006b084  call    WPP_SF_d
0x18006b089  lea     r11, [rsp+78h+var_28]
0x18006b08e  mov     eax, ebx
0x18006b090  mov     rbx, [r11+38h]
0x18006b094  mov     rbp, [r11+40h]
0x18006b098  mov     rsp, r11
0x18006b09b  pop     r15
0x18006b09d  pop     r14
0x18006b09f  pop     r12
0x18006b0a1  pop     rdi
0x18006b0a2  pop     rsi
0x18006b0a3  retn
```

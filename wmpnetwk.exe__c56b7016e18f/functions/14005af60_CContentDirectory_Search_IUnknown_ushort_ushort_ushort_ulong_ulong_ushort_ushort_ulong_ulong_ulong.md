# CContentDirectory::Search(IUnknown *,ushort *,ushort *,ushort *,ulong,ulong,ushort *,ushort * *,ulong *,ulong *,ulong *)

- ea: `0x14005af60`
- end: `0x14005b17d`
- name: `?Search@CContentDirectory@@UEAAJPEAUIUnknown@@PEAG11KK1PEAPEAGPEAK33@Z`
- size: `541`
- prototype: `int(CContentDirectory *__hidden this, struct IUnknown *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, unsigned __int16 *, unsigned __int16 **, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x14005af60`
- `0x14005c690`
- `0x14005e094`
- `0x140065d94`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14005b01b`
- `ADVAPI32!RegGetValueW` at `0x14005b01b`
- `KERNEL32!CompareStringOrdinal` at `0x14005b053`
- `KERNEL32!CompareStringOrdinal` at `0x14005b053`

## pseudocode

```c
__int64 __fastcall CContentDirectory::Search(
        CContentDirectory *this,
        struct IUnknown *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned __int16 *a8,
        unsigned __int16 **a9,
        unsigned int *a10,
        unsigned int *a11,
        unsigned int *a12)
{
  unsigned __int16 *v12; // r13
  int v16; // ebx
  unsigned int v17; // edi
  signed __int32 v18; // eax
  unsigned int *v19; // r14
  unsigned int *v20; // r15
  unsigned int v21; // ebx
  unsigned int v22; // eax
  int v23; // ecx
  DWORD pcbData[18]; // [rsp+60h] [rbp-48h] BYREF
  unsigned int pvData; // [rsp+B0h] [rbp+8h] BYREF
  struct IUnknown *v27; // [rsp+B8h] [rbp+10h]

  v27 = a2;
  v12 = a8;
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x40) != 0 )
    McTemplateU0zzqqzzqqq_EventWriteTransfer(
      (_DWORD)this,
      (unsigned int)CDS_Search_Start,
      (_DWORD)a3,
      (_DWORD)a4,
      a6,
      a7,
      (__int64)a5,
      (__int64)a8,
      0,
      0,
      0);
  pvData = 0;
  pcbData[0] = 4;
  v16 = 20;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0",
          L"MaxSearchBrowseOutstanding",
          0x18u,
          0,
          &pvData,
          pcbData) )
  {
    v16 = 0x7FFFFFFF;
    if ( pvData < 0x7FFFFFFF )
      v16 = pvData;
  }
  v17 = 6;
  if ( CompareStringOrdinal(a4, -1, L"*", 1, 0) != 2 )
    v17 = 1;
  v18 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 75, v17);
  v19 = a11;
  v20 = a10;
  if ( v18 > v16 )
  {
    v21 = -2147220616;
    ContentDirectoryErrors::SetCDErrorInfo(0x80040378);
  }
  else
  {
    v21 = CContentDirectory::internal_Search(this, v27, a3, a4, a5, a6, a7, v12, a9, a10, a11, a12);
  }
  _InterlockedAdd((volatile signed __int32 *)this + 75, -v17);
  if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x40) != 0 )
  {
    LOBYTE(v22) = -1;
    if ( v19 )
      v23 = *v19;
    else
      v23 = -1;
    if ( v20 )
      v22 = *v20;
    McTemplateU0zzqqzzqqq_EventWriteTransfer(
      v23,
      (unsigned int)CDS_Search_Stop,
      (_DWORD)a3,
      (_DWORD)a4,
      a6,
      a7,
      (__int64)a5,
      (__int64)v12,
      v22,
      v23,
      v21);
  }
  return v21;
}

```

## disassembly

```asm
0x14005af60  mov     rax, rsp
0x14005af63  mov     [rax+18h], rbx
0x14005af67  mov     [rax+10h], rdx
0x14005af6b  push    rbp
0x14005af6c  push    rsi
0x14005af6d  push    rdi
0x14005af6e  push    r12
0x14005af70  push    r13
0x14005af72  push    r14
0x14005af74  push    r15
0x14005af76  sub     rsp, 70h
0x14005af7a  mov     r13, [rsp+0A8h+arg_38]
0x14005af82  xor     edi, edi
0x14005af84  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 40h
0x14005af8b  mov     rbp, r9
0x14005af8e  mov     r12, r8
0x14005af91  mov     rsi, rcx
0x14005af94  jz      short loc_14005AFD2
0x14005af96  mov     [rax-58h], edi
0x14005af99  lea     rdx, CDS_Search_Start
0x14005afa0  mov     [rax-60h], edi
0x14005afa3  mov     [rax-68h], edi
0x14005afa6  mov     [rax-70h], r13
0x14005afaa  mov     rax, [rsp+0A8h+arg_20]
0x14005afb2  mov     [rsp+0A8h+pcbData], rax
0x14005afb7  mov     eax, [rsp+0A8h+arg_30]
0x14005afbe  mov     dword ptr [rsp+0A8h+pvData], eax
0x14005afc2  mov     eax, [rsp+0A8h+arg_28]
0x14005afc9  mov     dword ptr [rsp+0A8h+pdwType], eax
0x14005afcd  call    McTemplateU0zzqqzzqqq_EventWriteTransfer
0x14005afd2  lea     rax, [rsp+0A8h+var_48]
0x14005afd7  mov     [rsp+0A8h+arg_0], edi
0x14005afde  mov     [rsp+0A8h+pcbData], rax; pcbData
0x14005afe3  lea     r8, aMaxsearchbrows; "MaxSearchBrowseOutstanding"
0x14005afea  lea     rax, [rsp+0A8h+arg_0]
0x14005aff2  mov     [rsp+0A8h+var_48], 4
0x14005affa  mov     [rsp+0A8h+pvData], rax; pvData
0x14005afff  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Media Play"...
0x14005b006  mov     ebx, 14h
0x14005b00b  mov     [rsp+0A8h+pdwType], rdi; pdwType
0x14005b010  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14005b017  lea     r9d, [rbx+4]; dwFlags
0x14005b01b  call    cs:__imp_RegGetValueW
0x14005b021  test    eax, eax
0x14005b023  jnz     short loc_14005B039
0x14005b025  mov     ebx, 7FFFFFFFh
0x14005b02a  cmp     [rsp+0A8h+arg_0], ebx
0x14005b031  cmovb   ebx, [rsp+0A8h+arg_0]
0x14005b039  mov     r14d, 1
0x14005b03f  mov     dword ptr [rsp+0A8h+pdwType], edi; bIgnoreCase
0x14005b043  mov     r9d, r14d; cchCount2
0x14005b046  lea     r8, asc_1400A28A0; "*"
0x14005b04d  or      edx, 0FFFFFFFFh; cchCount1
0x14005b050  mov     rcx, rbp; lpString1
0x14005b053  call    cs:__imp_CompareStringOrdinal
0x14005b059  cmp     eax, 2
0x14005b05c  lea     edi, [r14+5]
0x14005b060  cmovnz  edi, r14d
0x14005b064  mov     eax, edi
0x14005b066  lock xadd [rsi+12Ch], eax
0x14005b06e  mov     r14, [rsp+0A8h+arg_50]
0x14005b076  mov     r15, [rsp+0A8h+arg_48]
0x14005b07e  cmp     eax, ebx
0x14005b080  jg      short loc_14005B0E8
0x14005b082  mov     rax, [rsp+0A8h+arg_58]
0x14005b08a  mov     r9, rbp; unsigned __int16 *
0x14005b08d  mov     rdx, [rsp+0A8h+arg_8]; struct IUnknown *
0x14005b095  mov     r8, r12; unsigned __int16 *
0x14005b098  mov     [rsp+0A8h+var_50], rax; unsigned int *
0x14005b09d  mov     rcx, rsi; this
0x14005b0a0  mov     rax, [rsp+0A8h+arg_40]
0x14005b0a8  mov     [rsp+0A8h+var_58], r14; unsigned int *
0x14005b0ad  mov     [rsp+0A8h+var_60], r15; unsigned int *
0x14005b0b2  mov     [rsp+0A8h+var_68], rax; unsigned __int16 **
0x14005b0b7  mov     eax, [rsp+0A8h+arg_30]
0x14005b0be  mov     [rsp+0A8h+var_70], r13; unsigned __int16 *
0x14005b0c3  mov     dword ptr [rsp+0A8h+pcbData], eax; unsigned int
0x14005b0c7  mov     eax, [rsp+0A8h+arg_28]
0x14005b0ce  mov     dword ptr [rsp+0A8h+pvData], eax; unsigned int
0x14005b0d2  mov     rax, [rsp+0A8h+arg_20]
0x14005b0da  mov     [rsp+0A8h+pdwType], rax; unsigned __int16 *
0x14005b0df  call    ?internal_Search@CContentDirectory@@AEAAJPEAUIUnknown@@PEAG11KK1PEAPEAGPEAK33@Z; CContentDirectory::internal_Search(IUnknown *,ushort *,ushort *,ushort *,ulong,ulong,ushort *,ushort * *,ulong *,ulong *,ulong *)
0x14005b0e4  mov     ebx, eax
0x14005b0e6  jmp     short loc_14005B0F4
0x14005b0e8  mov     ebx, 80040378h
0x14005b0ed  mov     ecx, ebx; int
0x14005b0ef  call    ?SetCDErrorInfo@ContentDirectoryErrors@@SAXJ@Z; ContentDirectoryErrors::SetCDErrorInfo(long)
0x14005b0f4  neg     edi
0x14005b0f6  lock add [rsi+12Ch], edi
0x14005b0fd  test    byte ptr cs:Microsoft_Windows_WMPNSS_ServiceEnableBits, 40h
0x14005b104  jz      short loc_14005B163
0x14005b106  or      eax, 0FFFFFFFFh
0x14005b109  test    r14, r14
0x14005b10c  jz      short loc_14005B113
0x14005b10e  mov     ecx, [r14]
0x14005b111  jmp     short loc_14005B115
0x14005b113  mov     ecx, eax
0x14005b115  test    r15, r15
0x14005b118  jz      short loc_14005B11D
0x14005b11a  mov     eax, [r15]
0x14005b11d  mov     dword ptr [rsp+0A8h+var_58], ebx
0x14005b121  lea     rdx, CDS_Search_Stop
0x14005b128  mov     dword ptr [rsp+0A8h+var_60], ecx
0x14005b12c  mov     r9, rbp
0x14005b12f  mov     dword ptr [rsp+0A8h+var_68], eax
0x14005b133  mov     r8, r12
0x14005b136  mov     rax, [rsp+0A8h+arg_20]
0x14005b13e  mov     [rsp+0A8h+var_70], r13
0x14005b143  mov     [rsp+0A8h+pcbData], rax
0x14005b148  mov     eax, [rsp+0A8h+arg_30]
0x14005b14f  mov     dword ptr [rsp+0A8h+pvData], eax
0x14005b153  mov     eax, [rsp+0A8h+arg_28]
0x14005b15a  mov     dword ptr [rsp+0A8h+pdwType], eax
0x14005b15e  call    McTemplateU0zzqqzzqqq_EventWriteTransfer
0x14005b163  mov     eax, ebx
0x14005b165  mov     rbx, [rsp+0A8h+arg_10]
0x14005b16d  add     rsp, 70h
0x14005b171  pop     r15
0x14005b173  pop     r14
0x14005b175  pop     r13
0x14005b177  pop     r12
0x14005b179  pop     rdi
0x14005b17a  pop     rsi
0x14005b17b  pop     rbp
0x14005b17c  retn
```

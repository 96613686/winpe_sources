# CTptControlPacket::AddClient(ushort const *,ulong,_WDSTPT_CLIENT *)

- ea: `0x1800218e0`
- end: `0x180021c0b`
- name: `?AddClient@CTptControlPacket@@QEAAKPEBGKPEAU_WDSTPT_CLIENT@@@Z`
- size: `811`
- prototype: `unsigned int __fastcall(CTptControlPacket *__hidden this, const unsigned __int16 *, unsigned int, struct _WDSTPT_CLIENT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180021c14`

## callees

- `0x180020558`
- `0x18002061c`
- `0x1800206e0`
- `0x180020f9c`
- `0x1800218e0`
- `0x180025850`

## string_xrefs

- `0x180021bc8`: `UserSid`

## pseudocode

```c
__int64 __fastcall CTptControlPacket::AddClient(
        CTptControlPacket *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct _WDSTPT_CLIENT *a4)
{
  unsigned int v7; // ebx
  const char *v8; // rdx
  const char *v9; // rdx
  const char *v10; // rdx
  const char *v11; // rdx
  const char *v12; // rdx
  const char *v13; // rdx
  const char *v14; // rdx
  const char *v15; // rdx
  const char *v16; // rdx
  const char *v17; // rdx
  const char *v18; // rdx
  const char *v19; // rdx
  const char *v20; // rdx
  int Src; // [rsp+20h] [rbp-38h]
  int Srca; // [rsp+20h] [rbp-38h]
  int Srcb; // [rsp+20h] [rbp-38h]
  size_t Size; // [rsp+28h] [rbp-30h]
  size_t Sizea; // [rsp+28h] [rbp-30h]
  size_t Sizeb; // [rsp+28h] [rbp-30h]

  v7 = CControlPacket::AddULONG64(this, L"CntList", L"NSHandle", a3, *(unsigned __int16 **)a4);
  if ( !ElValidateWin32(v7, v8, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x244u) )
  {
    v7 = CControlPacket::AddULONG64(this, L"CntList", L"CoHandle", a3, *((unsigned __int16 **)a4 + 1));
    if ( !ElValidateWin32(v7, v9, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x24Fu) )
    {
      v7 = CControlPacket::AddULONG64(this, L"CntList", L"SeHandle", a3, *((unsigned __int16 **)a4 + 2));
      if ( !ElValidateWin32(v7, v10, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x25Au) )
      {
        v7 = CControlPacket::AddULONG64(this, L"CntList", L"Handle", a3, *((unsigned __int16 **)a4 + 3));
        if ( !ElValidateWin32(v7, v11, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x265u) )
        {
          v7 = CControlPacket::AddString(this, L"CntList", L"Name", a3, *((const unsigned __int16 **)a4 + 4));
          if ( !ElValidateWin32(v7, v12, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x270u) )
          {
            LODWORD(Size) = *((_DWORD *)a4 + 19);
            v7 = CControlPacket::AddVariable<unsigned char>(
                   (int)this,
                   (int)L"CntList",
                   (int)L"IP",
                   a3,
                   Src,
                   Size,
                   (char *)a4 + 60);
            if ( !ElValidateWin32(v7, v13, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x27Bu) )
            {
              LODWORD(Sizea) = *((_DWORD *)a4 + 14);
              v7 = CControlPacket::AddVariable<unsigned char>(
                     (int)this,
                     (int)L"CntList",
                     (int)L"MAC",
                     a3,
                     Srca,
                     Sizea,
                     (char *)a4 + 40);
              if ( !ElValidateWin32(v7, v14, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x286u) )
              {
                v7 = CControlPacket::AddULONG(this, L"CntList", L"Progress", a3, *((_DWORD *)a4 + 20));
                if ( !ElValidateWin32(v7, v15, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x291u) )
                {
                  v7 = CControlPacket::AddULONG(this, L"CntList", L"TimeInSe", a3, *((_DWORD *)a4 + 21));
                  if ( !ElValidateWin32(v7, v16, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x29Cu) )
                  {
                    v7 = CControlPacket::AddULONG(this, L"CntList", L"CPU", a3, *((unsigned __int8 *)a4 + 2140));
                    if ( !ElValidateWin32(v7, v17, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x2A7u) )
                    {
                      v7 = CControlPacket::AddULONG(this, L"CntList", L"Memory", a3, *((unsigned __int8 *)a4 + 2141));
                      if ( !ElValidateWin32(v7, v18, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x2B2u) )
                      {
                        v7 = CControlPacket::AddULONG(this, L"CntList", L"Network", a3, *((unsigned __int8 *)a4 + 2142));
                        if ( !ElValidateWin32(v7, v19, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x2BDu) )
                        {
                          if ( *((_DWORD *)a4 + 534) )
                          {
                            LODWORD(Sizeb) = *((_DWORD *)a4 + 534);
                            v7 = CControlPacket::AddVariable<unsigned char>(
                                   (int)this,
                                   (int)L"CntList",
                                   (int)L"UserSid",
                                   a3,
                                   Srcb,
                                   Sizeb,
                                   (char *)a4 + 88);
                            ElValidateWin32(v7, v20, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x2CBu);
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
  return v7;
}

```

## disassembly

```asm
0x1800218e0  mov     r11, rsp
0x1800218e3  mov     [r11+8], rbx
0x1800218e7  mov     [r11+10h], rbp
0x1800218eb  mov     [r11+18h], rsi
0x1800218ef  push    rdi
0x1800218f0  push    r14
0x1800218f2  push    r15
0x1800218f4  sub     rsp, 40h
0x1800218f8  mov     rax, [r9]
0x1800218fb  lea     r14, aCntlist; "CntList"
0x180021902  mov     rdi, r9
0x180021905  mov     [r11-38h], rax
0x180021909  mov     r9d, r8d; unsigned int
0x18002190c  mov     esi, r8d
0x18002190f  lea     r8, aNshandle; "NSHandle"
0x180021916  mov     rdx, r14; unsigned __int16 *
0x180021919  mov     rbp, rcx
0x18002191c  call    ?AddULONG64@CControlPacket@@QEAAKPEBG0K_K@Z; CControlPacket::AddULONG64(ushort const *,ushort const *,ulong,unsigned __int64)
0x180021921  lea     r15, aBaseEcoWdsWdst; "base\\eco\\wds\\wdstptmgmt\\lib\\tptcon"...
0x180021928  mov     r9d, 244h; unsigned int
0x18002192e  mov     r8, r15; char *
0x180021931  mov     ecx, eax; unsigned int
0x180021933  mov     ebx, eax
0x180021935  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18002193a  test    eax, eax
0x18002193c  jnz     loc_180021BF0
0x180021942  mov     rax, [rdi+8]
0x180021946  lea     r8, aCohandle; "CoHandle"
0x18002194d  mov     r9d, esi; unsigned int
0x180021950  mov     qword ptr [rsp+58h+Src], rax; unsigned __int16 *
0x180021955  mov     rdx, r14; unsigned __int16 *
0x180021958  mov     rcx, rbp; this
0x18002195b  call    ?AddULONG64@CControlPacket@@QEAAKPEBG0K_K@Z; CControlPacket::AddULONG64(ushort const *,ushort const *,ulong,unsigned __int64)
0x180021960  mov     r9d, 24Fh; unsigned int
0x180021966  mov     r8, r15; char *
0x180021969  mov     ecx, eax; unsigned int
0x18002196b  mov     ebx, eax
0x18002196d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021972  test    eax, eax
0x180021974  jnz     loc_180021BF0
0x18002197a  mov     rax, [rdi+10h]
0x18002197e  lea     r8, aSehandle; "SeHandle"
0x180021985  mov     r9d, esi; unsigned int
0x180021988  mov     qword ptr [rsp+58h+Src], rax; unsigned __int16 *
0x18002198d  mov     rdx, r14; unsigned __int16 *
0x180021990  mov     rcx, rbp; this
0x180021993  call    ?AddULONG64@CControlPacket@@QEAAKPEBG0K_K@Z; CControlPacket::AddULONG64(ushort const *,ushort const *,ulong,unsigned __int64)
0x180021998  mov     r9d, 25Ah; unsigned int
0x18002199e  mov     r8, r15; char *
0x1800219a1  mov     ecx, eax; unsigned int
0x1800219a3  mov     ebx, eax
0x1800219a5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800219aa  test    eax, eax
0x1800219ac  jnz     loc_180021BF0
0x1800219b2  mov     rax, [rdi+18h]
0x1800219b6  lea     r8, aHandle; "Handle"
0x1800219bd  mov     r9d, esi; unsigned int
0x1800219c0  mov     qword ptr [rsp+58h+Src], rax; unsigned __int16 *
0x1800219c5  mov     rdx, r14; unsigned __int16 *
0x1800219c8  mov     rcx, rbp; this
0x1800219cb  call    ?AddULONG64@CControlPacket@@QEAAKPEBG0K_K@Z; CControlPacket::AddULONG64(ushort const *,ushort const *,ulong,unsigned __int64)
0x1800219d0  mov     r9d, 265h; unsigned int
0x1800219d6  mov     r8, r15; char *
0x1800219d9  mov     ecx, eax; unsigned int
0x1800219db  mov     ebx, eax
0x1800219dd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800219e2  test    eax, eax
0x1800219e4  jnz     loc_180021BF0
0x1800219ea  mov     rax, [rdi+20h]
0x1800219ee  lea     r8, aName; "Name"
0x1800219f5  mov     r9d, esi; unsigned int
0x1800219f8  mov     qword ptr [rsp+58h+Src], rax; int
0x1800219fd  mov     rdx, r14; unsigned __int16 *
0x180021a00  mov     rcx, rbp; this
0x180021a03  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x180021a08  mov     r9d, 270h; unsigned int
0x180021a0e  mov     r8, r15; char *
0x180021a11  mov     ecx, eax; unsigned int
0x180021a13  mov     ebx, eax
0x180021a15  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021a1a  test    eax, eax
0x180021a1c  jnz     loc_180021BF0
0x180021a22  lea     rax, [rdi+3Ch]
0x180021a26  mov     r9d, esi; int
0x180021a29  mov     [rsp+58h+var_28], rax; Src
0x180021a2e  lea     r8, aIp; "IP"
0x180021a35  mov     eax, [rax+10h]
0x180021a38  mov     rdx, r14; int
0x180021a3b  mov     rcx, rbp; int
0x180021a3e  mov     dword ptr [rsp+58h+Size], eax; Size
0x180021a42  call    ??$AddVariable@E@CControlPacket@@QEAAKPEBG0KKKPEAX@Z; CControlPacket::AddVariable<uchar>(ushort const *,ushort const *,ulong,ulong,ulong,void *)
0x180021a47  mov     r9d, 27Bh; unsigned int
0x180021a4d  mov     r8, r15; char *
0x180021a50  mov     ecx, eax; unsigned int
0x180021a52  mov     ebx, eax
0x180021a54  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021a59  test    eax, eax
0x180021a5b  jnz     loc_180021BF0
0x180021a61  lea     rax, [rdi+28h]
0x180021a65  mov     r9d, esi; int
0x180021a68  mov     [rsp+58h+var_28], rax; Src
0x180021a6d  lea     r8, aMac; "MAC"
0x180021a74  mov     eax, [rax+10h]
0x180021a77  mov     rdx, r14; int
0x180021a7a  mov     rcx, rbp; int
0x180021a7d  mov     dword ptr [rsp+58h+Size], eax; Size
0x180021a81  call    ??$AddVariable@E@CControlPacket@@QEAAKPEBG0KKKPEAX@Z; CControlPacket::AddVariable<uchar>(ushort const *,ushort const *,ulong,ulong,ulong,void *)
0x180021a86  mov     r9d, 286h; unsigned int
0x180021a8c  mov     r8, r15; char *
0x180021a8f  mov     ecx, eax; unsigned int
0x180021a91  mov     ebx, eax
0x180021a93  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021a98  test    eax, eax
0x180021a9a  jnz     loc_180021BF0
0x180021aa0  mov     eax, [rdi+50h]
0x180021aa3  lea     r8, aProgress; "Progress"
0x180021aaa  mov     r9d, esi; unsigned int
0x180021aad  mov     [rsp+58h+Src], eax; Src
0x180021ab1  mov     rdx, r14; unsigned __int16 *
0x180021ab4  mov     rcx, rbp; this
0x180021ab7  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x180021abc  mov     r9d, 291h; unsigned int
0x180021ac2  mov     r8, r15; char *
0x180021ac5  mov     ecx, eax; unsigned int
0x180021ac7  mov     ebx, eax
0x180021ac9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021ace  test    eax, eax
0x180021ad0  jnz     loc_180021BF0
0x180021ad6  mov     eax, [rdi+54h]
0x180021ad9  lea     r8, aTimeinse; "TimeInSe"
0x180021ae0  mov     r9d, esi; unsigned int
0x180021ae3  mov     [rsp+58h+Src], eax; Src
0x180021ae7  mov     rdx, r14; unsigned __int16 *
0x180021aea  mov     rcx, rbp; this
0x180021aed  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x180021af2  mov     r9d, 29Ch; unsigned int
0x180021af8  mov     r8, r15; char *
0x180021afb  mov     ecx, eax; unsigned int
0x180021afd  mov     ebx, eax
0x180021aff  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021b04  test    eax, eax
0x180021b06  jnz     loc_180021BF0
0x180021b0c  movzx   eax, byte ptr [rdi+85Ch]
0x180021b13  lea     r8, aCpu; "CPU"
0x180021b1a  mov     r9d, esi; unsigned int
0x180021b1d  mov     [rsp+58h+Src], eax; Src
0x180021b21  mov     rdx, r14; unsigned __int16 *
0x180021b24  mov     rcx, rbp; this
0x180021b27  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x180021b2c  mov     r9d, 2A7h; unsigned int
0x180021b32  mov     r8, r15; char *
0x180021b35  mov     ecx, eax; unsigned int
0x180021b37  mov     ebx, eax
0x180021b39  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021b3e  test    eax, eax
0x180021b40  jnz     loc_180021BF0
0x180021b46  movzx   eax, byte ptr [rdi+85Dh]
0x180021b4d  lea     r8, aMemory; "Memory"
0x180021b54  mov     r9d, esi; unsigned int
0x180021b57  mov     [rsp+58h+Src], eax; Src
0x180021b5b  mov     rdx, r14; unsigned __int16 *
0x180021b5e  mov     rcx, rbp; this
0x180021b61  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x180021b66  mov     r9d, 2B2h; unsigned int
0x180021b6c  mov     r8, r15; char *
0x180021b6f  mov     ecx, eax; unsigned int
0x180021b71  mov     ebx, eax
0x180021b73  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021b78  test    eax, eax
0x180021b7a  jnz     short loc_180021BF0
0x180021b7c  movzx   eax, byte ptr [rdi+85Eh]
0x180021b83  lea     r8, aNetwork; "Network"
0x180021b8a  mov     r9d, esi; unsigned int
0x180021b8d  mov     [rsp+58h+Src], eax; int
0x180021b91  mov     rdx, r14; unsigned __int16 *
0x180021b94  mov     rcx, rbp; this
0x180021b97  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x180021b9c  mov     r9d, 2BDh; unsigned int
0x180021ba2  mov     r8, r15; char *
0x180021ba5  mov     ecx, eax; unsigned int
0x180021ba7  mov     ebx, eax
0x180021ba9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021bae  test    eax, eax
0x180021bb0  jnz     short loc_180021BF0
0x180021bb2  mov     ecx, [rdi+858h]
0x180021bb8  test    ecx, ecx
0x180021bba  jz      short loc_180021BF0
0x180021bbc  lea     rax, [rdi+58h]
0x180021bc0  mov     r9d, esi; int
0x180021bc3  mov     [rsp+58h+var_28], rax; Src
0x180021bc8  lea     r8, aUsersid; "UserSid"
0x180021bcf  mov     dword ptr [rsp+58h+Size], ecx; Size
0x180021bd3  mov     rdx, r14; int
0x180021bd6  mov     rcx, rbp; int
0x180021bd9  call    ??$AddVariable@E@CControlPacket@@QEAAKPEBG0KKKPEAX@Z; CControlPacket::AddVariable<uchar>(ushort const *,ushort const *,ulong,ulong,ulong,void *)
0x180021bde  mov     r9d, 2CBh; unsigned int
0x180021be4  mov     r8, r15; char *
0x180021be7  mov     ecx, eax; unsigned int
0x180021be9  mov     ebx, eax
0x180021beb  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021bf0  mov     rbp, [rsp+58h+arg_8]
0x180021bf5  mov     eax, ebx
0x180021bf7  mov     rbx, [rsp+58h+arg_0]
0x180021bfc  mov     rsi, [rsp+58h+arg_10]
0x180021c01  add     rsp, 40h
0x180021c05  pop     r15
0x180021c07  pop     r14
0x180021c09  pop     rdi
0x180021c0a  retn
```

# CTptControlPacket::AddNamespace(ushort const *,ulong,_WDSTPT_NAMESPACE *)

- ea: `0x180021110`
- end: `0x180021449`
- name: `?AddNamespace@CTptControlPacket@@QEAAKPEBGKPEAU_WDSTPT_NAMESPACE@@@Z`
- size: `825`
- prototype: `unsigned int __fastcall(CTptControlPacket *__hidden this, const unsigned __int16 *, unsigned int, struct _WDSTPT_NAMESPACE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180021450`

## callees

- `0x180020558`
- `0x18002061c`
- `0x1800206e0`
- `0x1800207c8`
- `0x180021110`
- `0x180025850`

## string_xrefs

- `0x18002128c`: `Config`

## pseudocode

```c
__int64 __fastcall CTptControlPacket::AddNamespace(
        CTptControlPacket *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct _WDSTPT_NAMESPACE *a4)
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
  const char *v21; // rdx

  v7 = CControlPacket::AddULONG64(this, L"NSList", L"Handle", a3, *(unsigned __int16 **)a4);
  if ( !ElValidateWin32(v7, v8, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x42u) )
  {
    v7 = CControlPacket::AddULONG(this, L"NSList", L"Type", a3, *((_DWORD *)a4 + 2));
    if ( !ElValidateWin32(v7, v9, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x4Du) )
    {
      v7 = CControlPacket::AddString(this, L"NSList", L"Name", a3, *((const unsigned __int16 **)a4 + 2));
      if ( !ElValidateWin32(v7, v10, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x59u) )
      {
        v7 = CControlPacket::AddString(this, L"NSList", L"FName", a3, *((const unsigned __int16 **)a4 + 3));
        if ( !ElValidateWin32(v7, v11, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x64u) )
        {
          v7 = CControlPacket::AddString(this, L"NSList", L"Desc", a3, *((const unsigned __int16 **)a4 + 4));
          if ( !ElValidateWin32(v7, v12, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x6Fu) )
          {
            v7 = CControlPacket::AddString(this, L"NSList", L"CP", a3, *((const unsigned __int16 **)a4 + 5));
            if ( !ElValidateWin32(v7, v13, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x7Au) )
            {
              v7 = CControlPacket::AddString(this, L"NSList", L"Config", a3, *((const unsigned __int16 **)a4 + 6));
              if ( !ElValidateWin32(v7, v14, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x85u) )
              {
                v7 = CControlPacket::AddULONG(this, L"NSList", L"Started", a3, *((_DWORD *)a4 + 19));
                if ( !ElValidateWin32(v7, v15, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x90u) )
                {
                  v7 = CControlPacket::AddULONG(this, L"NSList", L"Tombstoned", a3, *((_DWORD *)a4 + 14));
                  if ( !ElValidateWin32(v7, v16, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x9Bu) )
                  {
                    v7 = CControlPacket::AddSYSTEMTIME(this, L"NSList", L"TsTime", a3, (SYSTEMTIME *)((char *)a4 + 60));
                    if ( !ElValidateWin32(v7, v17, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0xA6u) )
                    {
                      v7 = CControlPacket::AddULONG(this, L"NSList", L"Start.Type", a3, *((_DWORD *)a4 + 20));
                      if ( !ElValidateWin32(v7, v18, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0xB1u) )
                      {
                        v7 = CControlPacket::AddULONG(this, L"NSList", L"Start.Flags", a3, *((_DWORD *)a4 + 21));
                        if ( !ElValidateWin32(v7, v19, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0xBCu) )
                        {
                          v7 = CControlPacket::AddULONG(this, L"NSList", L"Start.MinClients", a3, *((_DWORD *)a4 + 22));
                          if ( !ElValidateWin32(v7, v20, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0xC7u) )
                          {
                            v7 = CControlPacket::AddSYSTEMTIME(
                                   this,
                                   L"NSList",
                                   L"Start.AbsTime",
                                   a3,
                                   (SYSTEMTIME *)((char *)a4 + 92));
                            ElValidateWin32(v7, v21, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0xD2u);
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
0x180021110  mov     r11, rsp
0x180021113  mov     [r11+8], rbx
0x180021117  mov     [r11+10h], rbp
0x18002111b  mov     [r11+18h], rsi
0x18002111f  push    rdi
0x180021120  push    r14
0x180021122  push    r15
0x180021124  sub     rsp, 30h
0x180021128  mov     rax, [r9]
0x18002112b  lea     r14, aNslist; "NSList"
0x180021132  mov     rdi, r9
0x180021135  mov     [r11-28h], rax
0x180021139  mov     r9d, r8d; unsigned int
0x18002113c  mov     esi, r8d
0x18002113f  lea     r8, aHandle; "Handle"
0x180021146  mov     rdx, r14; unsigned __int16 *
0x180021149  mov     rbp, rcx
0x18002114c  call    ?AddULONG64@CControlPacket@@QEAAKPEBG0K_K@Z; CControlPacket::AddULONG64(ushort const *,ushort const *,ulong,unsigned __int64)
0x180021151  lea     r15, aBaseEcoWdsWdst; "base\\eco\\wds\\wdstptmgmt\\lib\\tptcon"...
0x180021158  mov     r9d, 42h ; 'B'; unsigned int
0x18002115e  mov     r8, r15; char *
0x180021161  mov     ecx, eax; unsigned int
0x180021163  mov     ebx, eax
0x180021165  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18002116a  test    eax, eax
0x18002116c  jnz     loc_18002142E
0x180021172  mov     eax, [rdi+8]
0x180021175  lea     r8, aType; "Type"
0x18002117c  mov     r9d, esi; unsigned int
0x18002117f  mov     [rsp+48h+Src], eax; Src
0x180021183  mov     rdx, r14; unsigned __int16 *
0x180021186  mov     rcx, rbp; this
0x180021189  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x18002118e  mov     r9d, 4Dh ; 'M'; unsigned int
0x180021194  mov     r8, r15; char *
0x180021197  mov     ecx, eax; unsigned int
0x180021199  mov     ebx, eax
0x18002119b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800211a0  test    eax, eax
0x1800211a2  jnz     loc_18002142E
0x1800211a8  mov     rax, [rdi+10h]
0x1800211ac  lea     r8, aName; "Name"
0x1800211b3  mov     r9d, esi; unsigned int
0x1800211b6  mov     qword ptr [rsp+48h+Src], rax; unsigned __int16 *
0x1800211bb  mov     rdx, r14; unsigned __int16 *
0x1800211be  mov     rcx, rbp; this
0x1800211c1  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x1800211c6  mov     r9d, 59h ; 'Y'; unsigned int
0x1800211cc  mov     r8, r15; char *
0x1800211cf  mov     ecx, eax; unsigned int
0x1800211d1  mov     ebx, eax
0x1800211d3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800211d8  test    eax, eax
0x1800211da  jnz     loc_18002142E
0x1800211e0  mov     rax, [rdi+18h]
0x1800211e4  lea     r8, aFname; "FName"
0x1800211eb  mov     r9d, esi; unsigned int
0x1800211ee  mov     qword ptr [rsp+48h+Src], rax; unsigned __int16 *
0x1800211f3  mov     rdx, r14; unsigned __int16 *
0x1800211f6  mov     rcx, rbp; this
0x1800211f9  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x1800211fe  mov     r9d, 64h ; 'd'; unsigned int
0x180021204  mov     r8, r15; char *
0x180021207  mov     ecx, eax; unsigned int
0x180021209  mov     ebx, eax
0x18002120b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021210  test    eax, eax
0x180021212  jnz     loc_18002142E
0x180021218  mov     rax, [rdi+20h]
0x18002121c  lea     r8, aDesc; "Desc"
0x180021223  mov     r9d, esi; unsigned int
0x180021226  mov     qword ptr [rsp+48h+Src], rax; unsigned __int16 *
0x18002122b  mov     rdx, r14; unsigned __int16 *
0x18002122e  mov     rcx, rbp; this
0x180021231  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x180021236  mov     r9d, 6Fh ; 'o'; unsigned int
0x18002123c  mov     r8, r15; char *
0x18002123f  mov     ecx, eax; unsigned int
0x180021241  mov     ebx, eax
0x180021243  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021248  test    eax, eax
0x18002124a  jnz     loc_18002142E
0x180021250  mov     rax, [rdi+28h]
0x180021254  lea     r8, aCp; "CP"
0x18002125b  mov     r9d, esi; unsigned int
0x18002125e  mov     qword ptr [rsp+48h+Src], rax; unsigned __int16 *
0x180021263  mov     rdx, r14; unsigned __int16 *
0x180021266  mov     rcx, rbp; this
0x180021269  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x18002126e  mov     r9d, 7Ah ; 'z'; unsigned int
0x180021274  mov     r8, r15; char *
0x180021277  mov     ecx, eax; unsigned int
0x180021279  mov     ebx, eax
0x18002127b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021280  test    eax, eax
0x180021282  jnz     loc_18002142E
0x180021288  mov     rax, [rdi+30h]
0x18002128c  lea     r8, aConfig; "Config"
0x180021293  mov     r9d, esi; unsigned int
0x180021296  mov     qword ptr [rsp+48h+Src], rax; unsigned __int16 *
0x18002129b  mov     rdx, r14; unsigned __int16 *
0x18002129e  mov     rcx, rbp; this
0x1800212a1  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x1800212a6  mov     r9d, 85h; unsigned int
0x1800212ac  mov     r8, r15; char *
0x1800212af  mov     ecx, eax; unsigned int
0x1800212b1  mov     ebx, eax
0x1800212b3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800212b8  test    eax, eax
0x1800212ba  jnz     loc_18002142E
0x1800212c0  mov     eax, [rdi+4Ch]
0x1800212c3  lea     r8, aStarted; "Started"
0x1800212ca  mov     r9d, esi; unsigned int
0x1800212cd  mov     [rsp+48h+Src], eax; Src
0x1800212d1  mov     rdx, r14; unsigned __int16 *
0x1800212d4  mov     rcx, rbp; this
0x1800212d7  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x1800212dc  mov     r9d, 90h; unsigned int
0x1800212e2  mov     r8, r15; char *
0x1800212e5  mov     ecx, eax; unsigned int
0x1800212e7  mov     ebx, eax
0x1800212e9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800212ee  test    eax, eax
0x1800212f0  jnz     loc_18002142E
0x1800212f6  mov     eax, [rdi+38h]
0x1800212f9  lea     r8, aTombstoned; "Tombstoned"
0x180021300  mov     r9d, esi; unsigned int
0x180021303  mov     [rsp+48h+Src], eax; Src
0x180021307  mov     rdx, r14; unsigned __int16 *
0x18002130a  mov     rcx, rbp; this
0x18002130d  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x180021312  mov     r9d, 9Bh; unsigned int
0x180021318  mov     r8, r15; char *
0x18002131b  mov     ecx, eax; unsigned int
0x18002131d  mov     ebx, eax
0x18002131f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021324  test    eax, eax
0x180021326  jnz     loc_18002142E
0x18002132c  lea     rax, [rdi+3Ch]
0x180021330  mov     r9d, esi; unsigned int
0x180021333  lea     r8, aTstime_0; "TsTime"
0x18002133a  mov     qword ptr [rsp+48h+Src], rax; lpSystemTime
0x18002133f  mov     rdx, r14; unsigned __int16 *
0x180021342  mov     rcx, rbp; this
0x180021345  call    ?AddSYSTEMTIME@CControlPacket@@QEAAKPEBG0KPEAU_SYSTEMTIME@@@Z; CControlPacket::AddSYSTEMTIME(ushort const *,ushort const *,ulong,_SYSTEMTIME *)
0x18002134a  mov     r9d, 0A6h; unsigned int
0x180021350  mov     r8, r15; char *
0x180021353  mov     ecx, eax; unsigned int
0x180021355  mov     ebx, eax
0x180021357  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18002135c  test    eax, eax
0x18002135e  jnz     loc_18002142E
0x180021364  mov     eax, [rdi+50h]
0x180021367  lea     r8, aStartType; "Start.Type"
0x18002136e  mov     r9d, esi; unsigned int
0x180021371  mov     [rsp+48h+Src], eax; Src
0x180021375  mov     rdx, r14; unsigned __int16 *
0x180021378  mov     rcx, rbp; this
0x18002137b  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x180021380  mov     r9d, 0B1h; unsigned int
0x180021386  mov     r8, r15; char *
0x180021389  mov     ecx, eax; unsigned int
0x18002138b  mov     ebx, eax
0x18002138d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021392  test    eax, eax
0x180021394  jnz     loc_18002142E
0x18002139a  mov     eax, [rdi+54h]
0x18002139d  lea     r8, aStartFlags; "Start.Flags"
0x1800213a4  mov     r9d, esi; unsigned int
0x1800213a7  mov     [rsp+48h+Src], eax; Src
0x1800213ab  mov     rdx, r14; unsigned __int16 *
0x1800213ae  mov     rcx, rbp; this
0x1800213b1  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x1800213b6  mov     r9d, 0BCh; unsigned int
0x1800213bc  mov     r8, r15; char *
0x1800213bf  mov     ecx, eax; unsigned int
0x1800213c1  mov     ebx, eax
0x1800213c3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800213c8  test    eax, eax
0x1800213ca  jnz     short loc_18002142E
0x1800213cc  mov     eax, [rdi+58h]
0x1800213cf  lea     r8, aStartMinclient; "Start.MinClients"
0x1800213d6  mov     r9d, esi; unsigned int
0x1800213d9  mov     [rsp+48h+Src], eax; Src
0x1800213dd  mov     rdx, r14; unsigned __int16 *
0x1800213e0  mov     rcx, rbp; this
0x1800213e3  call    ?AddULONG@CControlPacket@@QEAAKPEBG0KK@Z; CControlPacket::AddULONG(ushort const *,ushort const *,ulong,ulong)
0x1800213e8  mov     r9d, 0C7h; unsigned int
0x1800213ee  mov     r8, r15; char *
0x1800213f1  mov     ecx, eax; unsigned int
0x1800213f3  mov     ebx, eax
0x1800213f5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800213fa  test    eax, eax
0x1800213fc  jnz     short loc_18002142E
0x1800213fe  lea     rax, [rdi+5Ch]
0x180021402  mov     r9d, esi; unsigned int
0x180021405  lea     r8, aStartAbstime; "Start.AbsTime"
0x18002140c  mov     qword ptr [rsp+48h+Src], rax; lpSystemTime
0x180021411  mov     rdx, r14; unsigned __int16 *
0x180021414  mov     rcx, rbp; this
0x180021417  call    ?AddSYSTEMTIME@CControlPacket@@QEAAKPEBG0KPEAU_SYSTEMTIME@@@Z; CControlPacket::AddSYSTEMTIME(ushort const *,ushort const *,ulong,_SYSTEMTIME *)
0x18002141c  mov     r9d, 0D2h; unsigned int
0x180021422  mov     r8, r15; char *
0x180021425  mov     ecx, eax; unsigned int
0x180021427  mov     ebx, eax
0x180021429  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18002142e  mov     rbp, [rsp+48h+arg_8]
0x180021433  mov     eax, ebx
0x180021435  mov     rbx, [rsp+48h+arg_0]
0x18002143a  mov     rsi, [rsp+48h+arg_10]
0x18002143f  add     rsp, 30h
0x180021443  pop     r15
0x180021445  pop     r14
0x180021447  pop     rdi
0x180021448  retn
```

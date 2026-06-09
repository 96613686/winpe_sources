# CTptControlPacket::GetNamespaceAt(ushort const *,ulong,_WDSTPT_NAMESPACE *)

- ea: `0x180021d80`
- end: `0x1800220f2`
- name: `?GetNamespaceAt@CTptControlPacket@@QEAAKPEBGKPEAU_WDSTPT_NAMESPACE@@@Z`
- size: `882`
- prototype: `unsigned int __fastcall(CTptControlPacket *__hidden this, const unsigned __int16 *, unsigned int, struct _WDSTPT_NAMESPACE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006488`

## callees

- `0x1800209c8`
- `0x180020b98`
- `0x180020bd0`
- `0x180020d58`
- `0x180021d80`
- `0x1800220f8`
- `0x180025850`
- `0x180026d46`

## string_xrefs

- `0x180021f15`: `Config`

## pseudocode

```c
__int64 __fastcall CTptControlPacket::GetNamespaceAt(
        CTptControlPacket *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct _WDSTPT_NAMESPACE *a4)
{
  unsigned int v6; // r9d
  unsigned int HANDLE; // ebx
  const char *v8; // rdx
  const char *v9; // rdx
  const char *v10; // rdx
  const char *v11; // rdx
  const char *v12; // rdx
  const char *v13; // rdx
  const char *v14; // rdx
  const char *v15; // rdx
  const char *v16; // rdx
  const unsigned __int16 *v17; // rdx
  unsigned int v18; // r9d
  const char *v19; // rdx
  const char *v20; // rdx
  const char *v21; // rdx
  const char *v22; // rdx
  const unsigned __int16 *v23; // rdx
  unsigned int v24; // r9d
  const char *v25; // rdx
  unsigned int v27; // [rsp+60h] [rbp+18h] BYREF

  v27 = 0;
  memset_0(a4, 0, 0x70u);
  HANDLE = CControlPacket::GetHANDLE(this, L"NSList", L"Handle", v6, (void **)a4);
  if ( !ElValidateWin32(HANDLE, v8, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x407u) )
  {
    HANDLE = CControlPacket::GetULONG(this, L"NSList", L"Type", 0, &v27);
    if ( !ElValidateWin32(HANDLE, v9, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x412u) )
    {
      *((_DWORD *)a4 + 2) = v27;
      HANDLE = CControlPacket::GetString(this, L"NSList", L"Name", 0, (unsigned __int16 **)a4 + 2);
      if ( !ElValidateWin32(HANDLE, v10, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x41Fu) )
      {
        HANDLE = CControlPacket::GetString(this, L"NSList", L"FName", 0, (unsigned __int16 **)a4 + 3);
        if ( !ElValidateWin32(HANDLE, v11, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x42Au) )
        {
          HANDLE = CControlPacket::GetString(this, L"NSList", L"Desc", 0, (unsigned __int16 **)a4 + 4);
          if ( !ElValidateWin32(HANDLE, v12, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x435u) )
          {
            HANDLE = CControlPacket::GetString(this, L"NSList", L"CP", 0, (unsigned __int16 **)a4 + 5);
            if ( !ElValidateWin32(HANDLE, v13, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x440u) )
            {
              HANDLE = CControlPacket::GetString(this, L"NSList", L"Config", 0, (unsigned __int16 **)a4 + 6);
              if ( !ElValidateWin32(HANDLE, v14, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x44Bu) )
              {
                HANDLE = CControlPacket::GetULONG(this, L"NSList", L"Started", 0, &v27);
                if ( !ElValidateWin32(HANDLE, v15, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x456u) )
                {
                  *((_DWORD *)a4 + 19) = v27;
                  HANDLE = CControlPacket::GetULONG(this, L"NSList", L"Tombstoned", 0, &v27);
                  if ( !ElValidateWin32(HANDLE, v16, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x463u) )
                  {
                    *((_DWORD *)a4 + 14) = v27;
                    HANDLE = CControlPacket::GetSYSTEMTIME(this, v17, L"TsTime", v18, (LPSYSTEMTIME)((char *)a4 + 60));
                    if ( !ElValidateWin32(HANDLE, v19, "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp", 0x470u) )
                    {
                      HANDLE = CControlPacket::GetULONG(this, L"NSList", L"Start.Type", 0, &v27);
                      if ( !ElValidateWin32(
                              HANDLE,
                              v20,
                              "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp",
                              0x47Bu) )
                      {
                        *((_DWORD *)a4 + 20) = v27;
                        HANDLE = CControlPacket::GetULONG(this, L"NSList", L"Start.Flags", 0, (unsigned int *)a4 + 21);
                        if ( !ElValidateWin32(
                                HANDLE,
                                v21,
                                "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp",
                                0x488u) )
                        {
                          HANDLE = CControlPacket::GetULONG(
                                     this,
                                     L"NSList",
                                     L"Start.MinClients",
                                     0,
                                     (unsigned int *)a4 + 22);
                          if ( !ElValidateWin32(
                                  HANDLE,
                                  v22,
                                  "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp",
                                  0x493u) )
                          {
                            HANDLE = CControlPacket::GetSYSTEMTIME(
                                       this,
                                       v23,
                                       L"Start.AbsTime",
                                       v24,
                                       (LPSYSTEMTIME)((char *)a4 + 92));
                            ElValidateWin32(
                              HANDLE,
                              v25,
                              "base\\eco\\wds\\wdstptmgmt\\lib\\tptcontrolpacket.cpp",
                              0x49Eu);
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
  if ( HANDLE && a4 )
    CTptControlPacket::FreeNamespace(a4, 0);
  return HANDLE;
}

```

## disassembly

```asm
0x180021d80  mov     rax, rsp
0x180021d83  mov     [rax+8], rbx
0x180021d87  mov     [rax+10h], rbp
0x180021d8b  mov     [rax+18h], r8d
0x180021d8f  push    rsi
0x180021d90  push    rdi
0x180021d91  push    r14
0x180021d93  sub     rsp, 30h
0x180021d97  and     dword ptr [rax+18h], 0
0x180021d9b  xor     edx, edx; Val
0x180021d9d  mov     rsi, rcx
0x180021da0  mov     rdi, r9
0x180021da3  mov     rcx, r9; void *
0x180021da6  lea     r8d, [rdx+70h]; Size
0x180021daa  call    memset_0
0x180021daf  lea     r14, aNslist; "NSList"
0x180021db6  mov     [rsp+48h+lpSystemTime], rdi; void **
0x180021dbb  mov     rdx, r14; unsigned __int16 *
0x180021dbe  lea     r8, aHandle; "Handle"
0x180021dc5  mov     rcx, rsi; this
0x180021dc8  call    ?GetHANDLE@CControlPacket@@QEAAKPEBG0KPEAPEAX@Z; CControlPacket::GetHANDLE(ushort const *,ushort const *,ulong,void * *)
0x180021dcd  lea     rbp, aBaseEcoWdsWdst; "base\\eco\\wds\\wdstptmgmt\\lib\\tptcon"...
0x180021dd4  mov     r9d, 407h; unsigned int
0x180021dda  mov     r8, rbp; char *
0x180021ddd  mov     ecx, eax; unsigned int
0x180021ddf  mov     ebx, eax
0x180021de1  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021de6  test    eax, eax
0x180021de8  jnz     loc_1800220CA
0x180021dee  lea     rax, [rsp+48h+arg_10]
0x180021df3  xor     r9d, r9d; unsigned int
0x180021df6  lea     r8, aType; "Type"
0x180021dfd  mov     [rsp+48h+lpSystemTime], rax; unsigned int *
0x180021e02  mov     rdx, r14; unsigned __int16 *
0x180021e05  mov     rcx, rsi; this
0x180021e08  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x180021e0d  mov     r9d, 412h; unsigned int
0x180021e13  mov     r8, rbp; char *
0x180021e16  mov     ecx, eax; unsigned int
0x180021e18  mov     ebx, eax
0x180021e1a  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021e1f  test    eax, eax
0x180021e21  jnz     loc_1800220CA
0x180021e27  mov     eax, [rsp+48h+arg_10]
0x180021e2b  lea     r8, aName; "Name"
0x180021e32  mov     [rdi+8], eax
0x180021e35  xor     r9d, r9d; unsigned int
0x180021e38  lea     rax, [rdi+10h]
0x180021e3c  mov     rdx, r14; unsigned __int16 *
0x180021e3f  mov     rcx, rsi; this
0x180021e42  mov     [rsp+48h+lpSystemTime], rax; unsigned __int16 **
0x180021e47  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x180021e4c  mov     r9d, 41Fh; unsigned int
0x180021e52  mov     r8, rbp; char *
0x180021e55  mov     ecx, eax; unsigned int
0x180021e57  mov     ebx, eax
0x180021e59  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021e5e  test    eax, eax
0x180021e60  jnz     loc_1800220CA
0x180021e66  lea     rax, [rdi+18h]
0x180021e6a  xor     r9d, r9d; unsigned int
0x180021e6d  lea     r8, aFname; "FName"
0x180021e74  mov     [rsp+48h+lpSystemTime], rax; unsigned __int16 **
0x180021e79  mov     rdx, r14; unsigned __int16 *
0x180021e7c  mov     rcx, rsi; this
0x180021e7f  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x180021e84  mov     r9d, 42Ah; unsigned int
0x180021e8a  mov     r8, rbp; char *
0x180021e8d  mov     ecx, eax; unsigned int
0x180021e8f  mov     ebx, eax
0x180021e91  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021e96  test    eax, eax
0x180021e98  jnz     loc_1800220CA
0x180021e9e  lea     rax, [rdi+20h]
0x180021ea2  xor     r9d, r9d; unsigned int
0x180021ea5  lea     r8, aDesc; "Desc"
0x180021eac  mov     [rsp+48h+lpSystemTime], rax; unsigned __int16 **
0x180021eb1  mov     rdx, r14; unsigned __int16 *
0x180021eb4  mov     rcx, rsi; this
0x180021eb7  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x180021ebc  mov     r9d, 435h; unsigned int
0x180021ec2  mov     r8, rbp; char *
0x180021ec5  mov     ecx, eax; unsigned int
0x180021ec7  mov     ebx, eax
0x180021ec9  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021ece  test    eax, eax
0x180021ed0  jnz     loc_1800220CA
0x180021ed6  lea     rax, [rdi+28h]
0x180021eda  xor     r9d, r9d; unsigned int
0x180021edd  lea     r8, aCp; "CP"
0x180021ee4  mov     [rsp+48h+lpSystemTime], rax; unsigned __int16 **
0x180021ee9  mov     rdx, r14; unsigned __int16 *
0x180021eec  mov     rcx, rsi; this
0x180021eef  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x180021ef4  mov     r9d, 440h; unsigned int
0x180021efa  mov     r8, rbp; char *
0x180021efd  mov     ecx, eax; unsigned int
0x180021eff  mov     ebx, eax
0x180021f01  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021f06  test    eax, eax
0x180021f08  jnz     loc_1800220CA
0x180021f0e  lea     rax, [rdi+30h]
0x180021f12  xor     r9d, r9d; unsigned int
0x180021f15  lea     r8, aConfig; "Config"
0x180021f1c  mov     [rsp+48h+lpSystemTime], rax; unsigned __int16 **
0x180021f21  mov     rdx, r14; unsigned __int16 *
0x180021f24  mov     rcx, rsi; this
0x180021f27  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x180021f2c  mov     r9d, 44Bh; unsigned int
0x180021f32  mov     r8, rbp; char *
0x180021f35  mov     ecx, eax; unsigned int
0x180021f37  mov     ebx, eax
0x180021f39  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021f3e  test    eax, eax
0x180021f40  jnz     loc_1800220CA
0x180021f46  lea     rax, [rsp+48h+arg_10]
0x180021f4b  xor     r9d, r9d; unsigned int
0x180021f4e  lea     r8, aStarted; "Started"
0x180021f55  mov     [rsp+48h+lpSystemTime], rax; unsigned int *
0x180021f5a  mov     rdx, r14; unsigned __int16 *
0x180021f5d  mov     rcx, rsi; this
0x180021f60  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x180021f65  mov     r9d, 456h; unsigned int
0x180021f6b  mov     r8, rbp; char *
0x180021f6e  mov     ecx, eax; unsigned int
0x180021f70  mov     ebx, eax
0x180021f72  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021f77  test    eax, eax
0x180021f79  jnz     loc_1800220CA
0x180021f7f  mov     eax, [rsp+48h+arg_10]
0x180021f83  lea     r8, aTombstoned; "Tombstoned"
0x180021f8a  mov     [rdi+4Ch], eax
0x180021f8d  xor     r9d, r9d; unsigned int
0x180021f90  lea     rax, [rsp+48h+arg_10]
0x180021f95  mov     rdx, r14; unsigned __int16 *
0x180021f98  mov     rcx, rsi; this
0x180021f9b  mov     [rsp+48h+lpSystemTime], rax; unsigned int *
0x180021fa0  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x180021fa5  mov     r9d, 463h; unsigned int
0x180021fab  mov     r8, rbp; char *
0x180021fae  mov     ecx, eax; unsigned int
0x180021fb0  mov     ebx, eax
0x180021fb2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021fb7  test    eax, eax
0x180021fb9  jnz     loc_1800220CA
0x180021fbf  mov     eax, [rsp+48h+arg_10]
0x180021fc3  lea     r8, aTstime_0; "TsTime"
0x180021fca  mov     [rdi+38h], eax
0x180021fcd  mov     rcx, rsi; this
0x180021fd0  lea     rax, [rdi+3Ch]
0x180021fd4  mov     [rsp+48h+lpSystemTime], rax; lpSystemTime
0x180021fd9  call    ?GetSYSTEMTIME@CControlPacket@@QEAAKPEBG0KPEAU_SYSTEMTIME@@@Z; CControlPacket::GetSYSTEMTIME(ushort const *,ushort const *,ulong,_SYSTEMTIME *)
0x180021fde  mov     r9d, 470h; unsigned int
0x180021fe4  mov     r8, rbp; char *
0x180021fe7  mov     ecx, eax; unsigned int
0x180021fe9  mov     ebx, eax
0x180021feb  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180021ff0  test    eax, eax
0x180021ff2  jnz     loc_1800220CA
0x180021ff8  lea     rax, [rsp+48h+arg_10]
0x180021ffd  xor     r9d, r9d; unsigned int
0x180022000  lea     r8, aStartType; "Start.Type"
0x180022007  mov     [rsp+48h+lpSystemTime], rax; unsigned int *
0x18002200c  mov     rdx, r14; unsigned __int16 *
0x18002200f  mov     rcx, rsi; this
0x180022012  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x180022017  mov     r9d, 47Bh; unsigned int
0x18002201d  mov     r8, rbp; char *
0x180022020  mov     ecx, eax; unsigned int
0x180022022  mov     ebx, eax
0x180022024  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180022029  test    eax, eax
0x18002202b  jnz     loc_1800220CA
0x180022031  mov     eax, [rsp+48h+arg_10]
0x180022035  lea     r8, aStartFlags; "Start.Flags"
0x18002203c  mov     [rdi+50h], eax
0x18002203f  xor     r9d, r9d; unsigned int
0x180022042  lea     rax, [rdi+54h]
0x180022046  mov     rdx, r14; unsigned __int16 *
0x180022049  mov     rcx, rsi; this
0x18002204c  mov     [rsp+48h+lpSystemTime], rax; unsigned int *
0x180022051  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x180022056  mov     r9d, 488h; unsigned int
0x18002205c  mov     r8, rbp; char *
0x18002205f  mov     ecx, eax; unsigned int
0x180022061  mov     ebx, eax
0x180022063  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180022068  test    eax, eax
0x18002206a  jnz     short loc_1800220CA
0x18002206c  lea     rax, [rdi+58h]
0x180022070  xor     r9d, r9d; unsigned int
0x180022073  lea     r8, aStartMinclient; "Start.MinClients"
0x18002207a  mov     [rsp+48h+lpSystemTime], rax; unsigned int *
0x18002207f  mov     rdx, r14; unsigned __int16 *
0x180022082  mov     rcx, rsi; this
0x180022085  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18002208a  mov     r9d, 493h; unsigned int
0x180022090  mov     r8, rbp; char *
0x180022093  mov     ecx, eax; unsigned int
0x180022095  mov     ebx, eax
0x180022097  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18002209c  test    eax, eax
0x18002209e  jnz     short loc_1800220CA
0x1800220a0  lea     rax, [rdi+5Ch]
0x1800220a4  mov     rcx, rsi; this
0x1800220a7  lea     r8, aStartAbstime; "Start.AbsTime"
0x1800220ae  mov     [rsp+48h+lpSystemTime], rax; lpSystemTime
0x1800220b3  call    ?GetSYSTEMTIME@CControlPacket@@QEAAKPEBG0KPEAU_SYSTEMTIME@@@Z; CControlPacket::GetSYSTEMTIME(ushort const *,ushort const *,ulong,_SYSTEMTIME *)
0x1800220b8  mov     r9d, 49Eh; unsigned int
0x1800220be  mov     r8, rbp; char *
0x1800220c1  mov     ecx, eax; unsigned int
0x1800220c3  mov     ebx, eax
0x1800220c5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800220ca  test    ebx, ebx
0x1800220cc  jz      short loc_1800220DD
0x1800220ce  test    rdi, rdi
0x1800220d1  jz      short loc_1800220DD
0x1800220d3  xor     edx, edx; int
0x1800220d5  mov     rcx, rdi; struct _WDSTPT_NAMESPACE *
0x1800220d8  call    ?FreeNamespace@CTptControlPacket@@SAXPEAU_WDSTPT_NAMESPACE@@H@Z; CTptControlPacket::FreeNamespace(_WDSTPT_NAMESPACE *,int)
0x1800220dd  mov     rbp, [rsp+48h+arg_8]
0x1800220e2  mov     eax, ebx
0x1800220e4  mov     rbx, [rsp+48h+arg_0]
0x1800220e9  add     rsp, 30h
0x1800220ed  pop     r14
0x1800220ef  pop     rdi
0x1800220f0  pop     rsi
0x1800220f1  retn
```

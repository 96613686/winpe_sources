# CTptControlPacket::GetNamespaceAt(ushort const *,ulong,_WDSTPT_NAMESPACE *)

- ea: `0x18001d0b4`
- end: `0x18001d408`
- name: `?GetNamespaceAt@CTptControlPacket@@QEAAKPEBGKPEAU_WDSTPT_NAMESPACE@@@Z`
- size: `852`
- prototype: `unsigned int __fastcall(CTptControlPacket *__hidden this, const unsigned __int16 *, unsigned int, struct _WDSTPT_NAMESPACE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001d018`

## callees

- `0x18001c9a4`
- `0x18001d0b4`
- `0x18001d67c`
- `0x18001e428`
- `0x18001e694`
- `0x18001e6ec`
- `0x18001e76c`
- `0x18001e9c2`

## string_xrefs

- `0x18001d236`: `Config`

## pseudocode

```c
__int64 __fastcall CTptControlPacket::GetNamespaceAt(
        CTptControlPacket *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct _WDSTPT_NAMESPACE *a4)
{
  unsigned int HANDLE; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  unsigned int v37; // [rsp+58h] [rbp+10h] BYREF
  int v38; // [rsp+5Ch] [rbp+14h]

  v38 = HIDWORD(a2);
  v37 = 0;
  memset_0(a4, 0, 0x70u);
  HANDLE = CControlPacket::GetHANDLE(this, L"NSList", L"Handle", a3, (void **)a4);
  if ( !(unsigned int)ElValidateWin32_15(HANDLE, v8, v9, 1031) )
  {
    HANDLE = CControlPacket::GetULONG(this, L"NSList", L"Type", a3, &v37);
    if ( !(unsigned int)ElValidateWin32_15(HANDLE, v10, v11, 1042) )
    {
      *((_DWORD *)a4 + 2) = v37;
      HANDLE = CControlPacket::GetString(this, L"NSList", L"Name", a3, (unsigned __int16 **)a4 + 2);
      if ( !(unsigned int)ElValidateWin32_15(HANDLE, v12, v13, 1055) )
      {
        HANDLE = CControlPacket::GetString(this, L"NSList", L"FName", a3, (unsigned __int16 **)a4 + 3);
        if ( !(unsigned int)ElValidateWin32_15(HANDLE, v14, v15, 1066) )
        {
          HANDLE = CControlPacket::GetString(this, L"NSList", L"Desc", a3, (unsigned __int16 **)a4 + 4);
          if ( !(unsigned int)ElValidateWin32_15(HANDLE, v16, v17, 1077) )
          {
            HANDLE = CControlPacket::GetString(this, L"NSList", L"CP", a3, (unsigned __int16 **)a4 + 5);
            if ( !(unsigned int)ElValidateWin32_15(HANDLE, v18, v19, 1088) )
            {
              HANDLE = CControlPacket::GetString(this, L"NSList", L"Config", a3, (unsigned __int16 **)a4 + 6);
              if ( !(unsigned int)ElValidateWin32_15(HANDLE, v20, v21, 1099) )
              {
                HANDLE = CControlPacket::GetULONG(this, L"NSList", L"Started", a3, &v37);
                if ( !(unsigned int)ElValidateWin32_15(HANDLE, v22, v23, 1110) )
                {
                  *((_DWORD *)a4 + 19) = v37;
                  HANDLE = CControlPacket::GetULONG(this, L"NSList", L"Tombstoned", a3, &v37);
                  if ( !(unsigned int)ElValidateWin32_15(HANDLE, v24, v25, 1123) )
                  {
                    *((_DWORD *)a4 + 14) = v37;
                    HANDLE = CControlPacket::GetSYSTEMTIME(
                               this,
                               L"NSList",
                               L"TsTime",
                               a3,
                               (LPSYSTEMTIME)((char *)a4 + 60));
                    if ( !(unsigned int)ElValidateWin32_15(HANDLE, v26, v27, 1136) )
                    {
                      HANDLE = CControlPacket::GetULONG(this, L"NSList", L"Start.Type", a3, &v37);
                      if ( !(unsigned int)ElValidateWin32_15(HANDLE, v28, v29, 1147) )
                      {
                        *((_DWORD *)a4 + 20) = v37;
                        HANDLE = CControlPacket::GetULONG(this, L"NSList", L"Start.Flags", a3, (unsigned int *)a4 + 21);
                        if ( !(unsigned int)ElValidateWin32_15(HANDLE, v30, v31, 1160) )
                        {
                          HANDLE = CControlPacket::GetULONG(
                                     this,
                                     L"NSList",
                                     L"Start.MinClients",
                                     a3,
                                     (unsigned int *)a4 + 22);
                          if ( !(unsigned int)ElValidateWin32_15(HANDLE, v32, v33, 1171) )
                          {
                            HANDLE = CControlPacket::GetSYSTEMTIME(
                                       this,
                                       L"NSList",
                                       L"Start.AbsTime",
                                       a3,
                                       (LPSYSTEMTIME)((char *)a4 + 92));
                            ElValidateWin32_15(HANDLE, v34, v35, 1182);
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
0x18001d0b4  mov     rax, rsp
0x18001d0b7  mov     [rax+8], rbx
0x18001d0bb  mov     [rax+18h], rbp
0x18001d0bf  mov     [rax+10h], rdx
0x18001d0c3  push    rsi
0x18001d0c4  push    rdi
0x18001d0c5  push    r14
0x18001d0c7  sub     rsp, 30h
0x18001d0cb  and     dword ptr [rax+10h], 0
0x18001d0cf  xor     edx, edx; Val
0x18001d0d1  mov     esi, r8d
0x18001d0d4  mov     rbp, rcx
0x18001d0d7  mov     rcx, r9; void *
0x18001d0da  mov     rdi, r9
0x18001d0dd  lea     r8d, [rdx+70h]; Size
0x18001d0e1  call    memset_0
0x18001d0e6  lea     r14, aNslist; "NSList"
0x18001d0ed  mov     [rsp+48h+lpSystemTime], rdi; void **
0x18001d0f2  mov     rdx, r14; unsigned __int16 *
0x18001d0f5  lea     r8, aHandle; "Handle"
0x18001d0fc  mov     r9d, esi; unsigned int
0x18001d0ff  mov     rcx, rbp; this
0x18001d102  call    ?GetHANDLE@CControlPacket@@QEAAKPEBG0KPEAPEAX@Z; CControlPacket::GetHANDLE(ushort const *,ushort const *,ulong,void * *)
0x18001d107  mov     r9d, 407h
0x18001d10d  mov     ecx, eax
0x18001d10f  mov     ebx, eax
0x18001d111  call    ElValidateWin32_15
0x18001d116  test    eax, eax
0x18001d118  jnz     loc_18001D3DF
0x18001d11e  lea     rax, [rsp+48h+arg_8]
0x18001d123  mov     r9d, esi; unsigned int
0x18001d126  lea     r8, aType; "Type"
0x18001d12d  mov     [rsp+48h+lpSystemTime], rax; unsigned int *
0x18001d132  mov     rdx, r14; unsigned __int16 *
0x18001d135  mov     rcx, rbp; this
0x18001d138  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001d13d  mov     r9d, 412h
0x18001d143  mov     ecx, eax
0x18001d145  mov     ebx, eax
0x18001d147  call    ElValidateWin32_15
0x18001d14c  test    eax, eax
0x18001d14e  jnz     loc_18001D3DF
0x18001d154  mov     eax, [rsp+48h+arg_8]
0x18001d158  lea     r8, aName; "Name"
0x18001d15f  mov     [rdi+8], eax
0x18001d162  mov     r9d, esi; unsigned int
0x18001d165  lea     rax, [rdi+10h]
0x18001d169  mov     rdx, r14; unsigned __int16 *
0x18001d16c  mov     rcx, rbp; this
0x18001d16f  mov     [rsp+48h+lpSystemTime], rax; unsigned __int16 **
0x18001d174  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x18001d179  mov     r9d, 41Fh
0x18001d17f  mov     ecx, eax
0x18001d181  mov     ebx, eax
0x18001d183  call    ElValidateWin32_15
0x18001d188  test    eax, eax
0x18001d18a  jnz     loc_18001D3DF
0x18001d190  lea     rax, [rdi+18h]
0x18001d194  mov     r9d, esi; unsigned int
0x18001d197  lea     r8, aFname; "FName"
0x18001d19e  mov     [rsp+48h+lpSystemTime], rax; unsigned __int16 **
0x18001d1a3  mov     rdx, r14; unsigned __int16 *
0x18001d1a6  mov     rcx, rbp; this
0x18001d1a9  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x18001d1ae  mov     r9d, 42Ah
0x18001d1b4  mov     ecx, eax
0x18001d1b6  mov     ebx, eax
0x18001d1b8  call    ElValidateWin32_15
0x18001d1bd  test    eax, eax
0x18001d1bf  jnz     loc_18001D3DF
0x18001d1c5  lea     rax, [rdi+20h]
0x18001d1c9  mov     r9d, esi; unsigned int
0x18001d1cc  lea     r8, aDesc; "Desc"
0x18001d1d3  mov     [rsp+48h+lpSystemTime], rax; unsigned __int16 **
0x18001d1d8  mov     rdx, r14; unsigned __int16 *
0x18001d1db  mov     rcx, rbp; this
0x18001d1de  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x18001d1e3  mov     r9d, 435h
0x18001d1e9  mov     ecx, eax
0x18001d1eb  mov     ebx, eax
0x18001d1ed  call    ElValidateWin32_15
0x18001d1f2  test    eax, eax
0x18001d1f4  jnz     loc_18001D3DF
0x18001d1fa  lea     rax, [rdi+28h]
0x18001d1fe  mov     r9d, esi; unsigned int
0x18001d201  lea     r8, aCp; "CP"
0x18001d208  mov     [rsp+48h+lpSystemTime], rax; unsigned __int16 **
0x18001d20d  mov     rdx, r14; unsigned __int16 *
0x18001d210  mov     rcx, rbp; this
0x18001d213  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x18001d218  mov     r9d, 440h
0x18001d21e  mov     ecx, eax
0x18001d220  mov     ebx, eax
0x18001d222  call    ElValidateWin32_15
0x18001d227  test    eax, eax
0x18001d229  jnz     loc_18001D3DF
0x18001d22f  lea     rax, [rdi+30h]
0x18001d233  mov     r9d, esi; unsigned int
0x18001d236  lea     r8, aConfig; "Config"
0x18001d23d  mov     [rsp+48h+lpSystemTime], rax; unsigned __int16 **
0x18001d242  mov     rdx, r14; unsigned __int16 *
0x18001d245  mov     rcx, rbp; this
0x18001d248  call    ?GetString@CControlPacket@@QEAAKPEBG0KPEAPEAG@Z; CControlPacket::GetString(ushort const *,ushort const *,ulong,ushort * *)
0x18001d24d  mov     r9d, 44Bh
0x18001d253  mov     ecx, eax
0x18001d255  mov     ebx, eax
0x18001d257  call    ElValidateWin32_15
0x18001d25c  test    eax, eax
0x18001d25e  jnz     loc_18001D3DF
0x18001d264  lea     rax, [rsp+48h+arg_8]
0x18001d269  mov     r9d, esi; unsigned int
0x18001d26c  lea     r8, aStarted; "Started"
0x18001d273  mov     [rsp+48h+lpSystemTime], rax; unsigned int *
0x18001d278  mov     rdx, r14; unsigned __int16 *
0x18001d27b  mov     rcx, rbp; this
0x18001d27e  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001d283  mov     r9d, 456h
0x18001d289  mov     ecx, eax
0x18001d28b  mov     ebx, eax
0x18001d28d  call    ElValidateWin32_15
0x18001d292  test    eax, eax
0x18001d294  jnz     loc_18001D3DF
0x18001d29a  mov     eax, [rsp+48h+arg_8]
0x18001d29e  lea     r8, aTombstoned; "Tombstoned"
0x18001d2a5  mov     [rdi+4Ch], eax
0x18001d2a8  mov     r9d, esi; unsigned int
0x18001d2ab  lea     rax, [rsp+48h+arg_8]
0x18001d2b0  mov     rdx, r14; unsigned __int16 *
0x18001d2b3  mov     rcx, rbp; this
0x18001d2b6  mov     [rsp+48h+lpSystemTime], rax; unsigned int *
0x18001d2bb  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001d2c0  mov     r9d, 463h
0x18001d2c6  mov     ecx, eax
0x18001d2c8  mov     ebx, eax
0x18001d2ca  call    ElValidateWin32_15
0x18001d2cf  test    eax, eax
0x18001d2d1  jnz     loc_18001D3DF
0x18001d2d7  mov     eax, [rsp+48h+arg_8]
0x18001d2db  lea     r8, aTstime_0; "TsTime"
0x18001d2e2  mov     [rdi+38h], eax
0x18001d2e5  mov     r9d, esi; unsigned int
0x18001d2e8  lea     rax, [rdi+3Ch]
0x18001d2ec  mov     rdx, r14; unsigned __int16 *
0x18001d2ef  mov     rcx, rbp; this
0x18001d2f2  mov     [rsp+48h+lpSystemTime], rax; lpSystemTime
0x18001d2f7  call    ?GetSYSTEMTIME@CControlPacket@@QEAAKPEBG0KPEAU_SYSTEMTIME@@@Z; CControlPacket::GetSYSTEMTIME(ushort const *,ushort const *,ulong,_SYSTEMTIME *)
0x18001d2fc  mov     r9d, 470h
0x18001d302  mov     ecx, eax
0x18001d304  mov     ebx, eax
0x18001d306  call    ElValidateWin32_15
0x18001d30b  test    eax, eax
0x18001d30d  jnz     loc_18001D3DF
0x18001d313  lea     rax, [rsp+48h+arg_8]
0x18001d318  mov     r9d, esi; unsigned int
0x18001d31b  lea     r8, aStartType; "Start.Type"
0x18001d322  mov     [rsp+48h+lpSystemTime], rax; unsigned int *
0x18001d327  mov     rdx, r14; unsigned __int16 *
0x18001d32a  mov     rcx, rbp; this
0x18001d32d  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001d332  mov     r9d, 47Bh
0x18001d338  mov     ecx, eax
0x18001d33a  mov     ebx, eax
0x18001d33c  call    ElValidateWin32_15
0x18001d341  test    eax, eax
0x18001d343  jnz     loc_18001D3DF
0x18001d349  mov     eax, [rsp+48h+arg_8]
0x18001d34d  lea     r8, aStartFlags; "Start.Flags"
0x18001d354  mov     [rdi+50h], eax
0x18001d357  mov     r9d, esi; unsigned int
0x18001d35a  lea     rax, [rdi+54h]
0x18001d35e  mov     rdx, r14; unsigned __int16 *
0x18001d361  mov     rcx, rbp; this
0x18001d364  mov     [rsp+48h+lpSystemTime], rax; unsigned int *
0x18001d369  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001d36e  mov     r9d, 488h
0x18001d374  mov     ecx, eax
0x18001d376  mov     ebx, eax
0x18001d378  call    ElValidateWin32_15
0x18001d37d  test    eax, eax
0x18001d37f  jnz     short loc_18001D3DF
0x18001d381  lea     rax, [rdi+58h]
0x18001d385  mov     r9d, esi; unsigned int
0x18001d388  lea     r8, aStartMinclient; "Start.MinClients"
0x18001d38f  mov     [rsp+48h+lpSystemTime], rax; unsigned int *
0x18001d394  mov     rdx, r14; unsigned __int16 *
0x18001d397  mov     rcx, rbp; this
0x18001d39a  call    ?GetULONG@CControlPacket@@QEAAKPEBG0KPEAK@Z; CControlPacket::GetULONG(ushort const *,ushort const *,ulong,ulong *)
0x18001d39f  mov     r9d, 493h
0x18001d3a5  mov     ecx, eax
0x18001d3a7  mov     ebx, eax
0x18001d3a9  call    ElValidateWin32_15
0x18001d3ae  test    eax, eax
0x18001d3b0  jnz     short loc_18001D3DF
0x18001d3b2  lea     rax, [rdi+5Ch]
0x18001d3b6  mov     r9d, esi; unsigned int
0x18001d3b9  lea     r8, aStartAbstime; "Start.AbsTime"
0x18001d3c0  mov     [rsp+48h+lpSystemTime], rax; lpSystemTime
0x18001d3c5  mov     rdx, r14; unsigned __int16 *
0x18001d3c8  mov     rcx, rbp; this
0x18001d3cb  call    ?GetSYSTEMTIME@CControlPacket@@QEAAKPEBG0KPEAU_SYSTEMTIME@@@Z; CControlPacket::GetSYSTEMTIME(ushort const *,ushort const *,ulong,_SYSTEMTIME *)
0x18001d3d0  mov     r9d, 49Eh
0x18001d3d6  mov     ecx, eax
0x18001d3d8  mov     ebx, eax
0x18001d3da  call    ElValidateWin32_15
0x18001d3df  test    ebx, ebx
0x18001d3e1  jz      short loc_18001D3F2
0x18001d3e3  test    rdi, rdi
0x18001d3e6  jz      short loc_18001D3F2
0x18001d3e8  xor     edx, edx; int
0x18001d3ea  mov     rcx, rdi; struct _WDSTPT_NAMESPACE *
0x18001d3ed  call    ?FreeNamespace@CTptControlPacket@@SAXPEAU_WDSTPT_NAMESPACE@@H@Z; CTptControlPacket::FreeNamespace(_WDSTPT_NAMESPACE *,int)
0x18001d3f2  mov     rbp, [rsp+48h+arg_10]
0x18001d3f7  mov     eax, ebx
0x18001d3f9  mov     rbx, [rsp+48h+arg_0]
0x18001d3fe  add     rsp, 30h
0x18001d402  pop     r14
0x18001d404  pop     rdi
0x18001d405  pop     rsi
0x18001d406  retn
```

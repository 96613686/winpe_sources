# CTptControlPacket::AddNamespace(ushort const *,ulong,_WDSTPT_NAMESPACE *)

- ea: `0x18001c558`
- end: `0x18001c85e`
- name: `?AddNamespace@CTptControlPacket@@QEAAKPEBGKPEAU_WDSTPT_NAMESPACE@@@Z`
- size: `774`
- prototype: `unsigned int __fastcall(CTptControlPacket *__hidden this, const unsigned __int16 *, unsigned int, struct _WDSTPT_NAMESPACE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001c864`

## callees

- `0x18001c558`
- `0x18001d67c`
- `0x18001dbb8`
- `0x18001dc74`
- `0x18001e0f0`
- `0x18001e168`

## string_xrefs

- `0x18001c6bc`: `Config`

## pseudocode

```c
__int64 __fastcall CTptControlPacket::AddNamespace(
        CTptControlPacket *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct _WDSTPT_NAMESPACE *a4)
{
  unsigned int v7; // ebx
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
  const unsigned __int16 *v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  const unsigned __int16 *v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // r8

  v7 = CControlPacket::AddVariable<unsigned __int64>((_DWORD)this, (unsigned int)L"NSList", (unsigned int)L"Handle", a3);
  if ( !(unsigned int)ElValidateWin32_15(v7, v8, v9, 66) )
  {
    v7 = CControlPacket::AddVariable<unsigned long>((_DWORD)this, (unsigned int)L"NSList", (unsigned int)L"Type", a3);
    if ( !(unsigned int)ElValidateWin32_15(v7, v10, v11, 77) )
    {
      v7 = CControlPacket::AddString(this, L"NSList", L"Name", a3, *((const unsigned __int16 **)a4 + 2));
      if ( !(unsigned int)ElValidateWin32_15(v7, v12, v13, 89) )
      {
        v7 = CControlPacket::AddString(this, L"NSList", L"FName", a3, *((const unsigned __int16 **)a4 + 3));
        if ( !(unsigned int)ElValidateWin32_15(v7, v14, v15, 100) )
        {
          v7 = CControlPacket::AddString(this, L"NSList", L"Desc", a3, *((const unsigned __int16 **)a4 + 4));
          if ( !(unsigned int)ElValidateWin32_15(v7, v16, v17, 111) )
          {
            v7 = CControlPacket::AddString(this, L"NSList", L"CP", a3, *((const unsigned __int16 **)a4 + 5));
            if ( !(unsigned int)ElValidateWin32_15(v7, v18, v19, 122) )
            {
              v7 = CControlPacket::AddString(this, L"NSList", L"Config", a3, *((const unsigned __int16 **)a4 + 6));
              if ( !(unsigned int)ElValidateWin32_15(v7, v20, v21, 133) )
              {
                v7 = CControlPacket::AddVariable<unsigned long>(
                       (_DWORD)this,
                       (unsigned int)L"NSList",
                       (unsigned int)L"Started",
                       a3);
                if ( !(unsigned int)ElValidateWin32_15(v7, v22, v23, 144) )
                {
                  v7 = CControlPacket::AddVariable<unsigned long>(
                         (_DWORD)this,
                         (unsigned int)L"NSList",
                         (unsigned int)L"Tombstoned",
                         a3);
                  if ( !(unsigned int)ElValidateWin32_15(v7, v24, v25, 155) )
                  {
                    v7 = CControlPacket::AddSYSTEMTIME(
                           this,
                           v26,
                           L"TsTime",
                           a3,
                           (struct _SYSTEMTIME *)((char *)a4 + 60));
                    if ( !(unsigned int)ElValidateWin32_15(v7, v27, v28, 166) )
                    {
                      v7 = CControlPacket::AddVariable<unsigned long>(
                             (_DWORD)this,
                             (unsigned int)L"NSList",
                             (unsigned int)L"Start.Type",
                             a3);
                      if ( !(unsigned int)ElValidateWin32_15(v7, v29, v30, 177) )
                      {
                        v7 = CControlPacket::AddVariable<unsigned long>(
                               (_DWORD)this,
                               (unsigned int)L"NSList",
                               (unsigned int)L"Start.Flags",
                               a3);
                        if ( !(unsigned int)ElValidateWin32_15(v7, v31, v32, 188) )
                        {
                          v7 = CControlPacket::AddVariable<unsigned long>(
                                 (_DWORD)this,
                                 (unsigned int)L"NSList",
                                 (unsigned int)L"Start.MinClients",
                                 a3);
                          if ( !(unsigned int)ElValidateWin32_15(v7, v33, v34, 199) )
                          {
                            v7 = CControlPacket::AddSYSTEMTIME(
                                   this,
                                   v35,
                                   L"Start.AbsTime",
                                   a3,
                                   (struct _SYSTEMTIME *)((char *)a4 + 92));
                            ElValidateWin32_15(v7, v36, v37, 210);
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
0x18001c558  mov     r11, rsp
0x18001c55b  mov     [r11+8], rbx
0x18001c55f  mov     [r11+10h], rbp
0x18001c563  mov     [r11+18h], rsi
0x18001c567  mov     [r11+20h], rdi
0x18001c56b  push    r14
0x18001c56d  sub     rsp, 30h
0x18001c571  mov     rax, [r9]
0x18001c574  lea     r14, aNslist; "NSList"
0x18001c57b  mov     rdi, r9
0x18001c57e  mov     [r11-10h], rax
0x18001c582  mov     r9d, r8d
0x18001c585  mov     esi, r8d
0x18001c588  lea     r8, aHandle; "Handle"
0x18001c58f  mov     rdx, r14
0x18001c592  mov     rbp, rcx
0x18001c595  call    ??$AddVariable@_K@CControlPacket@@QEAAKPEBG0KK_K@Z; CControlPacket::AddVariable<unsigned __int64>(ushort const *,ushort const *,ulong,ulong,unsigned __int64)
0x18001c59a  mov     r9d, 42h ; 'B'
0x18001c5a0  mov     ecx, eax
0x18001c5a2  mov     ebx, eax
0x18001c5a4  call    ElValidateWin32_15
0x18001c5a9  test    eax, eax
0x18001c5ab  jnz     loc_18001C840
0x18001c5b1  mov     eax, [rdi+8]
0x18001c5b4  lea     r8, aType; "Type"
0x18001c5bb  mov     r9d, esi
0x18001c5be  mov     [rsp+38h+var_10], eax
0x18001c5c2  mov     rdx, r14
0x18001c5c5  mov     rcx, rbp
0x18001c5c8  call    ??$AddVariable@K@CControlPacket@@QEAAKPEBG0KKK@Z; CControlPacket::AddVariable<ulong>(ushort const *,ushort const *,ulong,ulong,ulong)
0x18001c5cd  mov     r9d, 4Dh ; 'M'
0x18001c5d3  mov     ecx, eax
0x18001c5d5  mov     ebx, eax
0x18001c5d7  call    ElValidateWin32_15
0x18001c5dc  test    eax, eax
0x18001c5de  jnz     loc_18001C840
0x18001c5e4  mov     rax, [rdi+10h]
0x18001c5e8  lea     r8, aName; "Name"
0x18001c5ef  mov     r9d, esi; unsigned int
0x18001c5f2  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18001c5f7  mov     rdx, r14; unsigned __int16 *
0x18001c5fa  mov     rcx, rbp; this
0x18001c5fd  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x18001c602  mov     r9d, 59h ; 'Y'
0x18001c608  mov     ecx, eax
0x18001c60a  mov     ebx, eax
0x18001c60c  call    ElValidateWin32_15
0x18001c611  test    eax, eax
0x18001c613  jnz     loc_18001C840
0x18001c619  mov     rax, [rdi+18h]
0x18001c61d  lea     r8, aFname; "FName"
0x18001c624  mov     r9d, esi; unsigned int
0x18001c627  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18001c62c  mov     rdx, r14; unsigned __int16 *
0x18001c62f  mov     rcx, rbp; this
0x18001c632  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x18001c637  mov     r9d, 64h ; 'd'
0x18001c63d  mov     ecx, eax
0x18001c63f  mov     ebx, eax
0x18001c641  call    ElValidateWin32_15
0x18001c646  test    eax, eax
0x18001c648  jnz     loc_18001C840
0x18001c64e  mov     rax, [rdi+20h]
0x18001c652  lea     r8, aDesc; "Desc"
0x18001c659  mov     r9d, esi; unsigned int
0x18001c65c  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18001c661  mov     rdx, r14; unsigned __int16 *
0x18001c664  mov     rcx, rbp; this
0x18001c667  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x18001c66c  mov     r9d, 6Fh ; 'o'
0x18001c672  mov     ecx, eax
0x18001c674  mov     ebx, eax
0x18001c676  call    ElValidateWin32_15
0x18001c67b  test    eax, eax
0x18001c67d  jnz     loc_18001C840
0x18001c683  mov     rax, [rdi+28h]
0x18001c687  lea     r8, aCp; "CP"
0x18001c68e  mov     r9d, esi; unsigned int
0x18001c691  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18001c696  mov     rdx, r14; unsigned __int16 *
0x18001c699  mov     rcx, rbp; this
0x18001c69c  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x18001c6a1  mov     r9d, 7Ah ; 'z'
0x18001c6a7  mov     ecx, eax
0x18001c6a9  mov     ebx, eax
0x18001c6ab  call    ElValidateWin32_15
0x18001c6b0  test    eax, eax
0x18001c6b2  jnz     loc_18001C840
0x18001c6b8  mov     rax, [rdi+30h]
0x18001c6bc  lea     r8, aConfig; "Config"
0x18001c6c3  mov     r9d, esi; unsigned int
0x18001c6c6  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x18001c6cb  mov     rdx, r14; unsigned __int16 *
0x18001c6ce  mov     rcx, rbp; this
0x18001c6d1  call    ?AddString@CControlPacket@@QEAAKPEBG0K0@Z; CControlPacket::AddString(ushort const *,ushort const *,ulong,ushort const *)
0x18001c6d6  mov     r9d, 85h
0x18001c6dc  mov     ecx, eax
0x18001c6de  mov     ebx, eax
0x18001c6e0  call    ElValidateWin32_15
0x18001c6e5  test    eax, eax
0x18001c6e7  jnz     loc_18001C840
0x18001c6ed  mov     eax, [rdi+4Ch]
0x18001c6f0  lea     r8, aStarted; "Started"
0x18001c6f7  mov     r9d, esi
0x18001c6fa  mov     [rsp+38h+var_10], eax
0x18001c6fe  mov     rdx, r14
0x18001c701  mov     rcx, rbp
0x18001c704  call    ??$AddVariable@K@CControlPacket@@QEAAKPEBG0KKK@Z; CControlPacket::AddVariable<ulong>(ushort const *,ushort const *,ulong,ulong,ulong)
0x18001c709  mov     r9d, 90h
0x18001c70f  mov     ecx, eax
0x18001c711  mov     ebx, eax
0x18001c713  call    ElValidateWin32_15
0x18001c718  test    eax, eax
0x18001c71a  jnz     loc_18001C840
0x18001c720  mov     eax, [rdi+38h]
0x18001c723  lea     r8, aTombstoned; "Tombstoned"
0x18001c72a  mov     r9d, esi
0x18001c72d  mov     [rsp+38h+var_10], eax
0x18001c731  mov     rdx, r14
0x18001c734  mov     rcx, rbp
0x18001c737  call    ??$AddVariable@K@CControlPacket@@QEAAKPEBG0KKK@Z; CControlPacket::AddVariable<ulong>(ushort const *,ushort const *,ulong,ulong,ulong)
0x18001c73c  mov     r9d, 9Bh
0x18001c742  mov     ecx, eax
0x18001c744  mov     ebx, eax
0x18001c746  call    ElValidateWin32_15
0x18001c74b  test    eax, eax
0x18001c74d  jnz     loc_18001C840
0x18001c753  lea     rax, [rdi+3Ch]
0x18001c757  mov     r9d, esi; unsigned int
0x18001c75a  lea     r8, aTstime_0; "TsTime"
0x18001c761  mov     [rsp+38h+var_18], rax; struct _SYSTEMTIME *
0x18001c766  mov     rcx, rbp; this
0x18001c769  call    ?AddSYSTEMTIME@CControlPacket@@QEAAKPEBG0KPEAU_SYSTEMTIME@@@Z; CControlPacket::AddSYSTEMTIME(ushort const *,ushort const *,ulong,_SYSTEMTIME *)
0x18001c76e  mov     r9d, 0A6h
0x18001c774  mov     ecx, eax
0x18001c776  mov     ebx, eax
0x18001c778  call    ElValidateWin32_15
0x18001c77d  test    eax, eax
0x18001c77f  jnz     loc_18001C840
0x18001c785  mov     eax, [rdi+50h]
0x18001c788  lea     r8, aStartType; "Start.Type"
0x18001c78f  mov     r9d, esi
0x18001c792  mov     [rsp+38h+var_10], eax
0x18001c796  mov     rdx, r14
0x18001c799  mov     rcx, rbp
0x18001c79c  call    ??$AddVariable@K@CControlPacket@@QEAAKPEBG0KKK@Z; CControlPacket::AddVariable<ulong>(ushort const *,ushort const *,ulong,ulong,ulong)
0x18001c7a1  mov     r9d, 0B1h
0x18001c7a7  mov     ecx, eax
0x18001c7a9  mov     ebx, eax
0x18001c7ab  call    ElValidateWin32_15
0x18001c7b0  test    eax, eax
0x18001c7b2  jnz     loc_18001C840
0x18001c7b8  mov     eax, [rdi+54h]
0x18001c7bb  lea     r8, aStartFlags; "Start.Flags"
0x18001c7c2  mov     r9d, esi
0x18001c7c5  mov     [rsp+38h+var_10], eax
0x18001c7c9  mov     rdx, r14
0x18001c7cc  mov     rcx, rbp
0x18001c7cf  call    ??$AddVariable@K@CControlPacket@@QEAAKPEBG0KKK@Z; CControlPacket::AddVariable<ulong>(ushort const *,ushort const *,ulong,ulong,ulong)
0x18001c7d4  mov     r9d, 0BCh
0x18001c7da  mov     ecx, eax
0x18001c7dc  mov     ebx, eax
0x18001c7de  call    ElValidateWin32_15
0x18001c7e3  test    eax, eax
0x18001c7e5  jnz     short loc_18001C840
0x18001c7e7  mov     eax, [rdi+58h]
0x18001c7ea  lea     r8, aStartMinclient; "Start.MinClients"
0x18001c7f1  mov     r9d, esi
0x18001c7f4  mov     [rsp+38h+var_10], eax
0x18001c7f8  mov     rdx, r14
0x18001c7fb  mov     rcx, rbp
0x18001c7fe  call    ??$AddVariable@K@CControlPacket@@QEAAKPEBG0KKK@Z; CControlPacket::AddVariable<ulong>(ushort const *,ushort const *,ulong,ulong,ulong)
0x18001c803  mov     r9d, 0C7h
0x18001c809  mov     ecx, eax
0x18001c80b  mov     ebx, eax
0x18001c80d  call    ElValidateWin32_15
0x18001c812  test    eax, eax
0x18001c814  jnz     short loc_18001C840
0x18001c816  lea     rax, [rdi+5Ch]
0x18001c81a  mov     r9d, esi; unsigned int
0x18001c81d  lea     r8, aStartAbstime; "Start.AbsTime"
0x18001c824  mov     [rsp+38h+var_18], rax; struct _SYSTEMTIME *
0x18001c829  mov     rcx, rbp; this
0x18001c82c  call    ?AddSYSTEMTIME@CControlPacket@@QEAAKPEBG0KPEAU_SYSTEMTIME@@@Z; CControlPacket::AddSYSTEMTIME(ushort const *,ushort const *,ulong,_SYSTEMTIME *)
0x18001c831  mov     r9d, 0D2h
0x18001c837  mov     ecx, eax
0x18001c839  mov     ebx, eax
0x18001c83b  call    ElValidateWin32_15
0x18001c840  mov     rbp, [rsp+38h+arg_8]
0x18001c845  mov     eax, ebx
0x18001c847  mov     rbx, [rsp+38h+arg_0]
0x18001c84c  mov     rsi, [rsp+38h+arg_10]
0x18001c851  mov     rdi, [rsp+38h+arg_18]
0x18001c856  add     rsp, 30h
0x18001c85a  pop     r14
0x18001c85c  retn
```

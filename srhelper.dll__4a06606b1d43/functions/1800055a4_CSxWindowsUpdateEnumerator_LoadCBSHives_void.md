# CSxWindowsUpdateEnumerator::_LoadCBSHives(void)

- ea: `0x1800055a4`
- end: `0x180005723`
- name: `?_LoadCBSHives@CSxWindowsUpdateEnumerator@@AEAAJXZ`
- size: `383`
- prototype: `__int64 __fastcall(CSxWindowsUpdateEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18000408c`

## callees

- `0x180003ce0`
- `0x180003f80`
- `0x180004e20`
- `0x18000508c`
- `0x1800055a4`
- `0x18000572c`
- `0x180005c6c`
- `0x18000d348`
- `0x18000d43c`
- `0x180015390`
- `0x180015760`

## string_xrefs

- `0x1800055f7`: `CSxWindowsUpdateEnumerator::_LoadCBSHives`

## pseudocode

```c
__int64 __fastcall CSxWindowsUpdateEnumerator::_LoadCBSHives(CSxWindowsUpdateEnumerator *this)
{
  const unsigned __int16 *v2; // rcx
  const unsigned __int16 *v3; // r9
  unsigned int v4; // edi
  const unsigned __int16 *v5; // rdx
  __int64 (__fastcall *v6)(void *, __int64); // r9
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  const unsigned __int16 *v14; // [rsp+20h] [rbp-89h]
  void *v15; // [rsp+20h] [rbp-89h]
  struct CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *v16; // [rsp+28h] [rbp-81h]
  const unsigned __int16 *v17; // [rsp+30h] [rbp-79h]
  const unsigned __int16 *v18; // [rsp+38h] [rbp-71h]
  const unsigned __int16 *v19; // [rsp+40h] [rbp-69h]
  const unsigned __int16 *v20; // [rsp+48h] [rbp-61h]
  const unsigned __int16 *v21; // [rsp+50h] [rbp-59h]
  unsigned __int16 *v22[2]; // [rsp+60h] [rbp-49h] BYREF
  __int128 v23; // [rsp+70h] [rbp-39h] BYREF
  __int64 v24; // [rsp+80h] [rbp-29h]
  int HiveForCBS; // [rsp+88h] [rbp-21h] BYREF
  __int16 v26; // [rsp+8Ch] [rbp-1Dh]
  __int16 v27; // [rsp+8Eh] [rbp-1Bh]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&HiveForCBS,
    "CSxWindowsUpdateEnumerator::_LoadCBSHives",
    328);
  v2 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  v23 = 0;
  v24 = 0;
  CSxWindowsUpdateEnumerator::_CleanupOldHives(v2);
  v4 = 0;
  while ( 1 )
  {
    v5 = (const unsigned __int16 *)*((_QWORD *)this + 2);
    v22[0] = (unsigned __int16 *)qword_18001A620;
    v22[1] = 0;
    HiveForCBS = CBsString::SetPath(
                   (CBsString *)v22,
                   v5,
                   *((const unsigned __int16 **)&CSxWindowsUpdateEnumerator::s_hivesToMount + 2 * v4 + 1),
                   v3,
                   v14,
                   (const unsigned __int16 *)v16,
                   v17,
                   v18,
                   v19,
                   v20,
                   v21);
    if ( HiveForCBS < 0 )
      break;
    v6 = (__int64 (__fastcall *)(void *, __int64))*((_QWORD *)this + 5);
    v7 = (const unsigned __int16 *)*((_QWORD *)&CSxWindowsUpdateEnumerator::s_hivesToMount + 2 * v4);
    v8 = (const unsigned __int16 *)*((_QWORD *)this + 1);
    v15 = (void *)*((_QWORD *)this + 6);
    v26 = 340;
    HiveForCBS = CSxWindowsUpdateEnumerator::_LoadHiveForCBS(
                   v22[0],
                   v8,
                   v7,
                   v6,
                   v15,
                   (struct CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)&v23);
    if ( HiveForCBS < 0 )
    {
      v27 = 342;
      goto LABEL_13;
    }
    v9 = *(_QWORD *)this;
    v26 = 342;
    HiveForCBS = CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&public: static void CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&void SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>::Append(
                   v9,
                   &v23);
    if ( HiveForCBS < 0 )
    {
      v27 = 344;
      goto LABEL_13;
    }
    v26 = 344;
    CBsString::_Release((CBsString *)v22);
    if ( ++v4 >= 7 )
      goto LABEL_14;
  }
  v27 = 340;
LABEL_13:
  CBsString::_Release((CBsString *)v22);
LABEL_14:
  if ( HiveForCBS < 0 )
    CSxWindowsUpdateEnumerator::_UnloadCBSHives(this);
  CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation((LPVOID *)&v23);
  v10 = HiveForCBS;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&HiveForCBS, v11, v12);
  return v10;
}

```

## disassembly

```asm
0x1800055a4  push    rbp
0x1800055a6  push    rbx
0x1800055a7  push    rsi
0x1800055a8  push    rdi
0x1800055a9  push    r12
0x1800055ab  push    r13
0x1800055ad  push    r14
0x1800055af  push    r15
0x1800055b1  lea     rbp, [rsp-1Fh]
0x1800055b6  sub     rsp, 0C8h
0x1800055bd  mov     rbx, rcx
0x1800055c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055c7  lea     rax, WPP_GLOBAL_Control
0x1800055ce  cmp     rcx, rax
0x1800055d1  jz      short loc_1800055F1
0x1800055d3  test    dword ptr [rcx+1Ch], 20000000h
0x1800055da  jz      short loc_1800055F1
0x1800055dc  mov     rcx, [rcx+10h]
0x1800055e0  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x1800055e7  mov     edx, 0Fh
0x1800055ec  call    WPP_SF_
0x1800055f1  mov     r8d, 148h; unsigned __int16
0x1800055f7  lea     rdx, aCsxwindowsupda_4; "CSxWindowsUpdateEnumerator::_LoadCBSHiv"...
0x1800055fe  lea     rcx, [rbp+57h+var_78]; this
0x180005602  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180005607  mov     rcx, [rbx+8]; unsigned __int16 *
0x18000560b  xorps   xmm0, xmm0
0x18000560e  xor     eax, eax
0x180005610  movups  [rbp+57h+var_90], xmm0
0x180005614  mov     [rbp+57h+var_80], rax
0x180005618  call    ?_CleanupOldHives@CSxWindowsUpdateEnumerator@@CAJPEBG@Z; CSxWindowsUpdateEnumerator::_CleanupOldHives(ushort const *)
0x18000561d  mov     r12d, 154h
0x180005623  xor     edi, edi
0x180005625  lea     r15d, [r12+2]
0x18000562a  lea     r14d, [r12+4]
0x18000562f  mov     rdx, [rbx+10h]; unsigned __int16 *
0x180005633  lea     rax, qword_18001A620
0x18000563a  mov     esi, edi
0x18000563c  lea     r13, ?s_hivesToMount@CSxWindowsUpdateEnumerator@@0QBU_HIVE_LOAD_INFORMATION@1@B; CSxWindowsUpdateEnumerator::_HIVE_LOAD_INFORMATION const near * const CSxWindowsUpdateEnumerator::s_hivesToMount
0x180005643  add     rsi, rsi
0x180005646  mov     [rbp+57h+var_A0], rax
0x18000564a  lea     rcx, [rbp+57h+var_A0]; this
0x18000564e  mov     [rbp+57h+var_98], 0
0x180005656  mov     r8, [r13+rsi*8+8]; unsigned __int16 *
0x18000565b  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180005660  mov     [rbp+57h+var_78], eax
0x180005663  test    eax, eax
0x180005665  js      short loc_1800056DC
0x180005667  mov     r9, [rbx+28h]; int (__high *)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *)
0x18000566b  lea     rax, [rbp+57h+var_90]
0x18000566f  mov     r8, [r13+rsi*8+0]; unsigned __int16 *
0x180005674  mov     rdx, [rbx+8]; unsigned __int16 *
0x180005678  mov     rcx, [rbp+57h+var_A0]; unsigned __int16 *
0x18000567c  mov     [rsp+100h+var_D8], rax; struct CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *
0x180005681  mov     rax, [rbx+30h]
0x180005685  mov     [rsp+100h+var_E0], rax; void *
0x18000568a  mov     [rbp+57h+var_74], r12w
0x18000568f  call    ?_LoadHiveForCBS@CSxWindowsUpdateEnumerator@@CAJPEBG00P6AJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z1PEAU_CBS_LOADED_HIVE_INFORMATION@1@@Z; CSxWindowsUpdateEnumerator::_LoadHiveForCBS(ushort const *,ushort const *,ushort const *,long (*)(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *),void *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)
0x180005694  mov     [rbp+57h+var_78], eax
0x180005697  test    eax, eax
0x180005699  js      short loc_1800056D5
0x18000569b  mov     rcx, [rbx]
0x18000569e  lea     rdx, [rbp+57h+var_90]
0x1800056a2  mov     [rbp+57h+var_74], r15w
0x1800056a7  call    ?Append@?$CSxArrayBuilder@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@$1?_FreeCbsHiveLoadInformation@2@SAXPEAU12@@Z$1??$SxDefaultInit@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@@@YAX0@Z$1??$SxDefaultTransfer@U_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@@@YAX00@Z@@QEAAJPEAU_CBS_LOADED_HIVE_INFORMATION@CSxWindowsUpdateEnumerator@@@Z; CSxArrayBuilder<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION,&CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultInit<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *),&SxDefaultTransfer<CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION>(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *,CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)>::Append(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)
0x1800056ac  mov     [rbp+57h+var_78], eax
0x1800056af  lea     rcx, [rbp+57h+var_A0]; this
0x1800056b3  test    eax, eax
0x1800056b5  js      short loc_1800056CE
0x1800056b7  mov     [rbp+57h+var_74], r14w
0x1800056bc  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800056c1  inc     edi
0x1800056c3  cmp     edi, 7
0x1800056c6  jb      loc_18000562F
0x1800056cc  jmp     short loc_1800056EA
0x1800056ce  mov     [rbp+57h+var_72], r14w
0x1800056d3  jmp     short loc_1800056E5
0x1800056d5  mov     [rbp+57h+var_72], r15w
0x1800056da  jmp     short loc_1800056E1
0x1800056dc  mov     [rbp+57h+var_72], r12w
0x1800056e1  lea     rcx, [rbp+57h+var_A0]; this
0x1800056e5  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800056ea  cmp     [rbp+57h+var_78], 0
0x1800056ee  jge     short loc_1800056F8
0x1800056f0  mov     rcx, rbx; this
0x1800056f3  call    ?_UnloadCBSHives@CSxWindowsUpdateEnumerator@@AEAAJXZ; CSxWindowsUpdateEnumerator::_UnloadCBSHives(void)
0x1800056f8  lea     rcx, [rbp+57h+var_90]; struct CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *
0x1800056fc  call    ?_FreeCbsHiveLoadInformation@CSxWindowsUpdateEnumerator@@SAXPEAU_CBS_LOADED_HIVE_INFORMATION@1@@Z; CSxWindowsUpdateEnumerator::_FreeCbsHiveLoadInformation(CSxWindowsUpdateEnumerator::_CBS_LOADED_HIVE_INFORMATION *)
0x180005701  mov     ebx, [rbp+57h+var_78]
0x180005704  lea     rcx, [rbp+57h+var_78]; this
0x180005708  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000570d  mov     eax, ebx
0x18000570f  add     rsp, 0C8h
0x180005716  pop     r15
0x180005718  pop     r14
0x18000571a  pop     r13
0x18000571c  pop     r12
0x18000571e  pop     rdi
0x18000571f  pop     rsi
0x180005720  pop     rbx
0x180005721  pop     rbp
0x180005722  retn
```

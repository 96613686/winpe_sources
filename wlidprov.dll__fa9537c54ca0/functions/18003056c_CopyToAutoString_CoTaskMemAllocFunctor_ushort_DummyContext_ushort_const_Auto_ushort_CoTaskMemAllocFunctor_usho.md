# CopyToAutoString<CoTaskMemAllocFunctor<ushort *>,DummyContext>(ushort const *,Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext> &,unsigned __int64 *)

- ea: `0x18003056c`
- end: `0x180030639`
- name: `??$CopyToAutoString@V?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@YAJPEBGAEAV?$Auto@PEAGV?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@PEA_K@Z`
- size: `205`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033a70`

## callees

- `0x1800061a8`
- `0x18001633c`
- `0x18003056c`
- `0x180032b88`
- `0x180034ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800305c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800305c5`

## string_xrefs

- `0x180030614`: `CopyToAutoString`
- `0x1800305eb`: `hr = StringCbCopy(autoString, sizeInBytes, rawString)`

## pseudocode

```c
__int64 __fastcall CopyToAutoString<CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(
        unsigned __int16 *a1,
        unsigned __int16 **a2)
{
  int v4; // ebx
  const char *v5; // rax
  unsigned int v6; // r8d
  SIZE_T v7; // rbx
  unsigned __int16 *v8; // rax
  unsigned __int64 v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = 0;
  v4 = StringCbLengthW(a1, 0xFFFFFFFC, &v10);
  if ( v4 < 0 )
  {
    v5 = "hr = StringCbLength(rawString, STRSAFE_MAX_LENGTH * sizeof(WCHAR), &sizeInBytes)";
    v6 = 92;
LABEL_7:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
      "CopyToAutoString",
      v6,
      v4,
      v5);
    return (unsigned int)v4;
  }
  v7 = v10 + 2;
  Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>::Clear(a2);
  v8 = (unsigned __int16 *)CoTaskMemAlloc(v7);
  *a2 = v8;
  if ( !v8 )
  {
    v4 = -2147024882;
    v5 = "hr = autoString.Allocate(sizeInBytes)";
    v6 = 95;
    goto LABEL_7;
  }
  a2[1] = (unsigned __int16 *)v7;
  v4 = StringCbCopyW(v8, v7, a1);
  if ( v4 < 0 )
  {
    v5 = "hr = StringCbCopy(autoString, sizeInBytes, rawString)";
    v6 = 96;
    goto LABEL_7;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003056c  mov     rax, rsp
0x18003056f  mov     [rax+8], rbx
0x180030573  mov     [rax+10h], rsi
0x180030577  mov     [rax+18h], r8
0x18003057b  push    rdi
0x18003057c  sub     rsp, 30h
0x180030580  mov     rdi, rdx
0x180030583  mov     qword ptr [rax+18h], 0
0x18003058b  mov     edx, 0FFFFFFFCh; unsigned __int64
0x180030590  lea     r8, [rax+18h]; unsigned __int64 *
0x180030594  mov     rsi, rcx
0x180030597  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003059c  mov     ebx, eax
0x18003059e  test    eax, eax
0x1800305a0  jns     short loc_1800305B1
0x1800305a2  lea     rax, aHrStringcbleng_0; "hr = StringCbLength(rawString, STRSAFE_"...
0x1800305a9  mov     r8d, 5Ch ; '\'
0x1800305af  jmp     short loc_18003060C
0x1800305b1  mov     rbx, [rsp+38h+arg_10]
0x1800305b6  mov     rcx, rdi
0x1800305b9  add     rbx, 2
0x1800305bd  call    ?Clear@?$Auto@PEAGV?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@QEAAXXZ; Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext>::Clear(void)
0x1800305c2  mov     rcx, rbx; cb
0x1800305c5  call    cs:__imp_CoTaskMemAlloc
0x1800305cb  mov     [rdi], rax
0x1800305ce  test    rax, rax
0x1800305d1  jz      short loc_1800305FA
0x1800305d3  mov     [rdi+8], rbx
0x1800305d7  mov     r8, rsi; unsigned __int16 *
0x1800305da  mov     rdx, rbx; unsigned __int64
0x1800305dd  mov     rcx, rax; unsigned __int16 *
0x1800305e0  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800305e5  mov     ebx, eax
0x1800305e7  test    eax, eax
0x1800305e9  jns     short loc_180030627
0x1800305eb  lea     rax, aHrStringcbcopy_1; "hr = StringCbCopy(autoString, sizeInByt"...
0x1800305f2  mov     r8d, 60h ; '`'
0x1800305f8  jmp     short loc_18003060C
0x1800305fa  mov     ebx, 8007000Eh
0x1800305ff  lea     rax, aHrAutostringAl; "hr = autoString.Allocate(sizeInBytes)"
0x180030606  mov     r8d, 5Fh ; '_'; unsigned int
0x18003060c  mov     r9d, ebx; int
0x18003060f  mov     [rsp+38h+var_18], rax; char *
0x180030614  lea     rdx, aCopytoautostri; "CopyToAutoString"
0x18003061b  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180030622  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180030627  mov     rsi, [rsp+38h+arg_8]
0x18003062c  mov     eax, ebx
0x18003062e  mov     rbx, [rsp+38h+arg_0]
0x180030633  add     rsp, 30h
0x180030637  pop     rdi
0x180030638  retn
```

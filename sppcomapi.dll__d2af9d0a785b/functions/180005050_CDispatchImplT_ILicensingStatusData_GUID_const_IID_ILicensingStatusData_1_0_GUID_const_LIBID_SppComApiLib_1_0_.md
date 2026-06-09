# CDispatchImplT<ILicensingStatusData,&_GUID const IID_ILicensingStatusData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x180005050`
- end: `0x1800050e4`
- name: `?GetIDsOfNames@?$CDispatchImplT@UILicensingStatusData@@$1?IID_ILicensingStatusData@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x180005050`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CDispatchImplT<ILicensingStatusData,&_GUID const IID_ILicensingStatusData,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetIDsOfNames(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v6; // rax
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF

  v6 = *a1;
  v12 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64 *))(v6 + 32))(a1, 0, a5, &v12);
  v10 = v9;
  if ( v9 < 0
    || (v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v12 + 80LL))(v12, a3, a4, a6),
        v10 = v9,
        v9 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return v10;
}

```

## disassembly

```asm
0x180005050  mov     r11, rsp
0x180005053  mov     [r11+10h], rbx
0x180005057  mov     [r11+18h], rsi
0x18000505b  push    rdi
0x18000505c  sub     rsp, 30h
0x180005060  mov     rax, [rcx]
0x180005063  mov     edi, r9d
0x180005066  mov     rsi, r8
0x180005069  mov     qword ptr [r11+8], 0
0x180005071  mov     r8d, [rsp+38h+arg_20]
0x180005076  lea     r9, [r11+8]
0x18000507a  xor     edx, edx
0x18000507c  mov     rax, [rax+20h]
0x180005080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005085  mov     ebx, eax
0x180005087  test    eax, eax
0x180005089  js      short loc_1800050AD
0x18000508b  mov     rcx, [rsp+38h+arg_0]
0x180005090  mov     r8d, edi
0x180005093  mov     r9, [rsp+38h+arg_28]
0x180005098  mov     rdx, rsi
0x18000509b  mov     rax, [rcx]
0x18000509e  mov     rax, [rax+50h]
0x1800050a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050a7  mov     ebx, eax
0x1800050a9  test    eax, eax
0x1800050ab  jns     short loc_1800050B4
0x1800050ad  mov     ecx, eax
0x1800050af  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800050b4  mov     ecx, ebx
0x1800050b6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800050bb  mov     rcx, [rsp+38h+arg_0]
0x1800050c0  test    rcx, rcx
0x1800050c3  jz      short loc_1800050D1
0x1800050c5  mov     rax, [rcx]
0x1800050c8  mov     rax, [rax+10h]
0x1800050cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d1  mov     rsi, [rsp+38h+arg_10]
0x1800050d6  mov     eax, ebx
0x1800050d8  mov     rbx, [rsp+38h+arg_8]
0x1800050dd  add     rsp, 30h
0x1800050e1  pop     rdi
0x1800050e2  retn
```

# CVssRegistryKey::GetValue(ushort const *,__int64 &,bool)

- ea: `0x180039f5c`
- end: `0x18003a056`
- name: `?GetValue@CVssRegistryKey@@QEAA_NPEBGAEA_J_N@Z`
- size: `250`
- prototype: `char __fastcall(CVssRegistryKey *this, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18002e7ec`

## callees

- `0x18000212c`
- `0x180003718`
- `0x180015864`
- `0x18001febc`
- `0x180033a8c`
- `0x180033c78`
- `0x180039ac8`
- `0x180039f5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18003a015`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18003a015`

## string_xrefs

- `0x180039f79`: `base\stor\vss\modules\registry\registry.cxx`
- `0x180039f85`: `CVssRegistryKey::GetValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall CVssRegistryKey::GetValue(CVssRegistryKey *this, const unsigned __int16 *a2, __int64 *a3)
{
  unsigned __int16 **Ref; // rax
  const unsigned __int16 *v6; // rdx
  bool v7; // r9
  char v8; // dl
  char v9; // bl
  void **v11; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t *String; // [rsp+28h] [rbp-D8h]
  _QWORD v13[3]; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+48h] [rbp-B8h]
  int v15; // [rsp+4Ch] [rbp-B4h]
  int v16; // [rsp+50h] [rbp-B0h]
  _BYTE v17[120]; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+D0h] [rbp-30h]
  LPVOID v19[14]; // [rsp+E0h] [rbp-20h] BYREF

  v13[0] = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v13[1] = L"CVssRegistryKey::GetValue";
  v13[2] = L"REGREGSC";
  v14 = 474;
  v15 = 11;
  v16 = 255;
  v18 = 0x1000000;
  memset_0(v17, 0, sizeof(v17));
  CVssFunctionTracer::CVssFunctionTracer((__int64)v19, (__int64)v13, 0);
  String = 0;
  v11 = &CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::`vftable';
  Ref = (unsigned __int16 **)CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::ResetAndGetRef(&v11);
  if ( CVssRegistryKey::GetValue(this, v6, Ref, v7) )
  {
    *a3 = _wtoi64(String);
    v8 = 1;
  }
  else
  {
    v8 = 0;
  }
  v9 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v19, v8);
  CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<unsigned short *,CVssAllocatingPtr_Storage<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),void * (*)(unsigned __int64),&void * CoTaskMemAlloc(unsigned __int64)>>(&v11);
  CVssFunctionTracer::~CVssFunctionTracer(v19);
  return v9;
}

```

## disassembly

```asm
0x180039f5c  mov     [rsp-8+arg_0], rbx
0x180039f61  mov     [rsp-8+arg_10], rdi
0x180039f66  push    rbp
0x180039f67  lea     rbp, [rsp-50h]
0x180039f6c  sub     rsp, 150h
0x180039f73  mov     rdi, r8
0x180039f76  mov     rbx, rcx
0x180039f79  lea     rax, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x180039f80  mov     [rsp+150h+var_120], rax
0x180039f85  lea     rax, aCvssregistryke_3; "CVssRegistryKey::GetValue"
0x180039f8c  mov     [rsp+150h+var_118], rax
0x180039f91  lea     rax, aRegregsc; "REGREGSC"
0x180039f98  mov     [rsp+150h+var_110], rax
0x180039f9d  mov     [rsp+150h+var_108], 1DAh
0x180039fa5  mov     [rsp+150h+var_104], 0Bh
0x180039fad  mov     [rsp+150h+var_100], 0FFh
0x180039fb5  mov     [rbp+50h+var_80], 1000000h
0x180039fbc  xor     edx, edx; Val
0x180039fbe  lea     r8d, [rdx+78h]; Size
0x180039fc2  lea     rcx, [rsp+150h+var_F8]; void *
0x180039fc7  call    memset_0
0x180039fcc  xor     r8d, r8d
0x180039fcf  lea     rdx, [rsp+150h+var_120]
0x180039fd4  lea     rcx, [rbp+50h+var_70]
0x180039fd8  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x180039fdd  nop
0x180039fde  mov     [rsp+150h+String], 0
0x180039fe7  lea     rax, ??_7?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@6B@; const CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::`vftable'
0x180039fee  mov     [rsp+150h+var_130], rax
0x180039ff3  lea     rcx, [rsp+150h+var_130]
0x180039ff8  call    ?ResetAndGetRef@?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@QEAAAEAPEAGXZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::ResetAndGetRef(void)
0x180039ffd  mov     r8, rax; unsigned __int16 **
0x18003a000  mov     rcx, rbx; this
0x18003a003  call    ?GetValue@CVssRegistryKey@@QEAA_NPEBGAEAPEAG_N@Z; CVssRegistryKey::GetValue(ushort const *,ushort * &,bool)
0x18003a008  test    al, al
0x18003a00a  jnz     short loc_18003A010
0x18003a00c  xor     edx, edx
0x18003a00e  jmp     short loc_18003A020
0x18003a010  mov     rcx, [rsp+150h+String]; String
0x18003a015  call    cs:__imp__wtoi64
0x18003a01b  mov     [rdi], rax
0x18003a01e  mov     dl, 1; bool
0x18003a020  lea     rcx, [rbp+50h+var_70]; this
0x18003a024  call    ?Exit@CVssFunctionTracer@@QEAA_N_N@Z; CVssFunctionTracer::Exit(bool)
0x18003a029  mov     bl, al
0x18003a02b  lea     rcx, [rsp+150h+var_130]
0x18003a030  call    ??1?$CVssAuto@PEAGV?$CVssAllocatingPtr_Storage@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZP6APEAX_K@Z$1?CoTaskMemAlloc@@YAPEAX1@Z@@@@UEAA@XZ; CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>::~CVssAuto<ushort *,CVssAllocatingPtr_Storage<ushort *,void (*)(void *),&CoTaskMemFree(void *),void * (*)(unsigned __int64),&CoTaskMemAlloc(unsigned __int64)>>(void)
0x18003a035  nop
0x18003a036  lea     rcx, [rbp+50h+var_70]; this
0x18003a03a  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18003a03f  mov     al, bl
0x18003a041  lea     r11, [rsp+150h+var_s0]
0x18003a049  mov     rbx, [r11+10h]
0x18003a04d  mov     rdi, [r11+20h]
0x18003a051  mov     rsp, r11
0x18003a054  pop     rbp
0x18003a055  retn
```

# CWMIBinMof::AddThisMofToRegistryIfNeeded(ushort *,ushort *,ulong &,ulong &,int)

- ea: `0x1800174ec`
- end: `0x180017642`
- name: `?AddThisMofToRegistryIfNeeded@CWMIBinMof@@QEAAJPEAG0AEAK1H@Z`
- size: `342`
- prototype: `__int64 __fastcall(CWMIBinMof *this, unsigned __int16 *, unsigned __int16 *, unsigned int *, unsigned int *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001154`
- `0x180002478`

## callees

- `0x1800021f0`
- `0x1800034f0`
- `0x180003958`
- `0x1800039c4`
- `0x180003b08`
- `0x180004194`
- `0x1800079f0`
- `0x1800174ec`
- `0x18001ce18`
- `0x18001ceec`
- `0x18001d0b0`
- `0x18001d3a0`

## string_xrefs

- `0x1800175ad`: `LowDateTime:%ld,HighDateTime:%ld***Binary mof compiled successfully`

## pseudocode

```c
__int64 __fastcall CWMIBinMof::AddThisMofToRegistryIfNeeded(
        CWMIBinMof *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        unsigned int *a5,
        int a6)
{
  unsigned int v8; // edi
  unsigned __int16 *v9; // rbx
  const unsigned __int16 *v10; // r8
  unsigned int v11; // ebx
  __int64 v13; // [rsp+20h] [rbp-E0h]
  _BYTE v14[8]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v15; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[608]; // [rsp+50h] [rbp-B0h] BYREF

  v8 = -2147217407;
  CRegistry::CRegistry((CRegistry *)v16);
  if ( !CRegistry::CreateOpen((CRegistry *)v16, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\WDM", 0, 0, 2u, 0, 0) )
  {
    CAutoWChar::CAutoWChar((CAutoWChar *)&v15, 260);
    v9 = v15;
    if ( v15 )
    {
      v10 = L"LowDateTime:%ld,HighDateTime:%ld***Binary mof compiled successfully";
      if ( !a6 )
        v10 = L"LowDateTime:%ld,HighDateTime:%ld***Binary mof failed, see WMIPROV.LOG";
      LODWORD(v13) = *a5;
      StringCchPrintfW(v15, 0x104u, v10, *a4, v13);
      CHString::CHString((CHString *)v14, v9);
      v11 = CRegistry::SetCurrentKeyValue((CRegistry *)v16, a3, (struct CHString *)v14);
      CHString::~CHString((CHString *)v14);
      v8 = v11 != 0 ? 0x80041001 : 0;
    }
    else
    {
      v8 = -2147217402;
    }
    CAutoWChar::~CAutoWChar((void **)&v15);
  }
  CRegistry::Close((CRegistry *)v16);
  CRegistry::~CRegistry((CRegistry *)v16);
  return v8;
}

```

## disassembly

```asm
0x1800174ec  mov     [rsp-8+arg_0], rbx
0x1800174f1  push    rbp
0x1800174f2  push    rsi
0x1800174f3  push    rdi
0x1800174f4  push    r14
0x1800174f6  push    r15
0x1800174f8  lea     rbp, [rsp-1C0h]
0x180017500  sub     rsp, 2C0h
0x180017507  mov     rax, cs:__security_cookie
0x18001750e  xor     rax, rsp
0x180017511  mov     [rbp+1E0h+var_30], rax
0x180017518  mov     rsi, r9
0x18001751b  mov     r15, r8
0x18001751e  mov     r14, [rbp+1E0h+arg_20]
0x180017525  mov     edi, 80041001h
0x18001752a  lea     rcx, [rsp+2E0h+var_290]; this
0x18001752f  call    ??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x180017534  nop
0x180017535  mov     [rsp+2E0h+var_2A8], 0; unsigned int *
0x18001753e  mov     [rsp+2E0h+var_2B0], 0; struct _SECURITY_ATTRIBUTES *
0x180017547  mov     [rsp+2E0h+var_2B8], 2; unsigned int
0x18001754f  mov     dword ptr [rsp+2E0h+var_2C0], 0; unsigned int
0x180017557  xor     r9d, r9d; unsigned __int16 *
0x18001755a  lea     r8, aSoftwareMicros; "Software\\Microsoft\\WBEM\\WDM"
0x180017561  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180017568  lea     rcx, [rsp+2E0h+var_290]; this
0x18001756d  call    ?CreateOpen@CRegistry@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CRegistry::CreateOpen(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180017572  test    eax, eax
0x180017574  jnz     loc_180017605
0x18001757a  mov     edx, 104h; int
0x18001757f  lea     rcx, [rsp+2E0h+var_298]; this
0x180017584  call    ??0CAutoWChar@@QEAA@H@Z; CAutoWChar::CAutoWChar(int)
0x180017589  nop
0x18001758a  mov     rbx, [rsp+2E0h+var_298]
0x18001758f  test    rbx, rbx
0x180017592  jz      short loc_1800175F6
0x180017594  mov     eax, [r14]
0x180017597  mov     dword ptr [rsp+2E0h+var_2C0], eax
0x18001759b  mov     r9d, [rsi]
0x18001759e  mov     edx, 104h; unsigned __int64
0x1800175a3  mov     rcx, rbx; unsigned __int16 *
0x1800175a6  cmp     [rbp+1E0h+arg_28], 0
0x1800175ad  lea     r8, aLowdatetimeLdH; "LowDateTime:%ld,HighDateTime:%ld***Bina"...
0x1800175b4  jnz     short loc_1800175BD
0x1800175b6  lea     r8, aLowdatetimeLdH_1; "LowDateTime:%ld,HighDateTime:%ld***Bina"...
0x1800175bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800175c2  mov     rdx, rbx; unsigned __int16 *
0x1800175c5  lea     rcx, [rsp+2E0h+var_2A0]; this
0x1800175ca  call    ??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x1800175cf  nop
0x1800175d0  lea     r8, [rsp+2E0h+var_2A0]; struct CHString *
0x1800175d5  mov     rdx, r15; unsigned __int16 *
0x1800175d8  lea     rcx, [rsp+2E0h+var_290]; this
0x1800175dd  call    ?SetCurrentKeyValue@CRegistry@@QEAAKPEBGAEAVCHString@@@Z; CRegistry::SetCurrentKeyValue(ushort const *,CHString &)
0x1800175e2  mov     ebx, eax
0x1800175e4  lea     rcx, [rsp+2E0h+var_2A0]; this
0x1800175e9  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800175ee  neg     ebx
0x1800175f0  sbb     eax, eax
0x1800175f2  and     edi, eax
0x1800175f4  jmp     short loc_1800175FB
0x1800175f6  mov     edi, 80041006h
0x1800175fb  lea     rcx, [rsp+2E0h+var_298]; this
0x180017600  call    ??1CAutoWChar@@QEAA@XZ; CAutoWChar::~CAutoWChar(void)
0x180017605  lea     rcx, [rsp+2E0h+var_290]; this
0x18001760a  call    ?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x18001760f  nop
0x180017610  lea     rcx, [rsp+2E0h+var_290]; this
0x180017615  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18001761a  mov     eax, edi
0x18001761c  mov     rcx, [rbp+1E0h+var_30]
0x180017623  xor     rcx, rsp; StackCookie
0x180017626  call    __security_check_cookie
0x18001762b  mov     rbx, [rsp+2E0h+arg_0]
0x180017633  add     rsp, 2C0h
0x18001763a  pop     r15
0x18001763c  pop     r14
0x18001763e  pop     rdi
0x18001763f  pop     rsi
0x180017640  pop     rbp
0x180017641  retn
```

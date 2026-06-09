# RegisterTaskNotification(ushort const *,ushort const *,ushort const *,ulong,ushort *)

- ea: `0x180011f40`
- end: `0x18001220c`
- name: `?RegisterTaskNotification@@YAJPEBG00KPEAG@Z`
- size: `716`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800058f0`
- `0x180007488`
- `0x18000878c`
- `0x180009c00`
- `0x180009cd4`
- `0x180009d18`
- `0x18000c8f4`
- `0x18000d414`
- `0x18000fd94`
- `0x180010388`
- `0x180011464`
- `0x180011f40`
- `0x18001c0f4`
- `0x180020118`
- `0x18002e5b0`

## import_xrefs

- `msvcrt!wcschr` at `0x180011fd2`
- `msvcrt!wcschr` at `0x180011fd2`

## pseudocode

```c
__int64 __fastcall RegisterTaskNotification(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  const unsigned __int16 *v7; // rdi
  const wchar_t *v8; // rax
  int v10; // eax
  void *v11; // rax
  __int64 v12; // rax
  TaskXmlReader *v13; // rbx
  int v14; // eax
  unsigned int v15; // [rsp+30h] [rbp-318h]
  TaskXmlReader *v16; // [rsp+38h] [rbp-310h] BYREF
  __int64 v17; // [rsp+40h] [rbp-308h] BYREF
  void **pExceptionObject; // [rsp+48h] [rbp-300h] BYREF
  char v19; // [rsp+50h] [rbp-2F8h]
  char *v20; // [rsp+58h] [rbp-2F0h]
  __int64 v21; // [rsp+60h] [rbp-2E8h]
  __int64 v22; // [rsp+68h] [rbp-2E0h]
  int v23; // [rsp+70h] [rbp-2D8h]
  __int64 v24; // [rsp+74h] [rbp-2D4h]
  void **v25; // [rsp+80h] [rbp-2C8h] BYREF
  char v26; // [rsp+88h] [rbp-2C0h]
  char *v27; // [rsp+90h] [rbp-2B8h]
  __int64 v28; // [rsp+98h] [rbp-2B0h]
  __int64 v29; // [rsp+A0h] [rbp-2A8h]
  int v30; // [rsp+A8h] [rbp-2A0h]
  __int64 v31; // [rsp+ACh] [rbp-29Ch]
  void **v32; // [rsp+B8h] [rbp-290h] BYREF
  char v33; // [rsp+C0h] [rbp-288h]
  char *v34; // [rsp+C8h] [rbp-280h]
  __int64 v35; // [rsp+D0h] [rbp-278h]
  __int64 v36; // [rsp+D8h] [rbp-270h]
  int v37; // [rsp+E0h] [rbp-268h]
  __int64 v38; // [rsp+E4h] [rbp-264h]
  _BYTE v39[544]; // [rsp+100h] [rbp-248h] BYREF

  v7 = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids, a1);
  }
  if ( v7 )
  {
    v8 = v7 + 1;
    if ( *v7 != 92 )
      v8 = v7;
    v7 = v8;
    if ( wcschr(v8, 0x5Cu) )
      return 1;
  }
  if ( RegistrationGuard::IsGuarded(v7, a2) )
    return 0;
  if ( !CompatibilityAdapter::GetAdapter() )
    return 2147549183LL;
  v17 = 0;
  v10 = StringReader::CreateStream(a2, &v17);
  if ( v10 < 0 )
  {
    v19 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v20 = byte_1800505F8;
    v21 = 0;
    v22 = 0;
    v23 = v10;
    v24 = -1;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v16 = 0;
  v11 = operator new(0x460u);
  if ( v11 )
  {
    v12 = TaskXmlReader::TaskXmlReader(v11, &v17);
    v13 = (TaskXmlReader *)v12;
    if ( v12 )
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
  }
  else
  {
    v13 = 0;
  }
  wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(&v16);
  v16 = v13;
  if ( !v13 )
  {
    v26 = 0;
    v27 = byte_1800505F8;
    v28 = 0;
    v29 = 0;
    v30 = 14;
    v31 = -1;
    v25 = &wmi::GenericException::`vftable';
    throw (wmi::OutOfMemoryException *)&v25;
  }
  BinXmlHandler::BinXmlHandler((BinXmlHandler *)v39, v7, a5, a4);
  v14 = TaskXmlReader::ProcessXml(v13, (struct ITaskXmlHandler *)v39);
  if ( v14 < 0 )
  {
    v33 = 0;
    v32 = &wmi::GenericException::`vftable';
    v34 = byte_1800505F8;
    v35 = 0;
    v36 = 0;
    v37 = v14;
    v38 = -1;
    throw (wmi::GenericException *)&v32;
  }
  v15 = BinXmlHandler::SaveLegacyTask((BinXmlHandler *)v39);
  BinXmlHandler::~BinXmlHandler((BinXmlHandler *)v39);
  wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(&v16);
  ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v17);
  return v15;
}

```

## disassembly

```asm
0x180011f40  mov     [rsp+arg_10], rbx
0x180011f45  mov     [rsp+arg_18], rsi
0x180011f4a  push    rdi
0x180011f4b  push    r14
0x180011f4d  push    r15
0x180011f4f  sub     rsp, 330h
0x180011f56  mov     rax, cs:__security_cookie
0x180011f5d  xor     rax, rsp
0x180011f60  mov     [rsp+348h+var_28], rax
0x180011f68  mov     esi, r9d
0x180011f6b  mov     rbx, rdx
0x180011f6e  mov     rdi, rcx
0x180011f71  mov     r14, [rsp+348h+arg_20]
0x180011f79  xor     r15d, r15d
0x180011f7c  mov     [rsp+348h+var_318], r15d
0x180011f81  lea     rax, WPP_GLOBAL_Control
0x180011f88  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f8f  cmp     rcx, rax
0x180011f92  jz      short loc_180011FB7
0x180011f94  test    byte ptr [rcx+1Ch], 2
0x180011f98  jz      short loc_180011FB7
0x180011f9a  cmp     byte ptr [rcx+19h], 4
0x180011f9e  jb      short loc_180011FB7
0x180011fa0  lea     edx, [r15+28h]
0x180011fa4  mov     r9, rdi
0x180011fa7  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180011fae  mov     rcx, [rcx+10h]
0x180011fb2  call    WPP_SF_S
0x180011fb7  test    rdi, rdi
0x180011fba  jz      short loc_180011FE7
0x180011fbc  lea     rax, [rdi+2]
0x180011fc0  mov     edx, 5Ch ; '\'; Ch
0x180011fc5  cmp     [rdi], dx
0x180011fc8  cmovnz  rax, rdi
0x180011fcc  mov     rdi, rax
0x180011fcf  mov     rcx, rax; Str
0x180011fd2  call    cs:__imp_wcschr
0x180011fd8  test    rax, rax
0x180011fdb  jz      short loc_180011FE7
0x180011fdd  mov     eax, 1
0x180011fe2  jmp     loc_1800121E2
0x180011fe7  mov     rdx, rbx; unsigned __int16 *
0x180011fea  mov     rcx, rdi; unsigned __int16 *
0x180011fed  call    ?IsGuarded@RegistrationGuard@@SA_NPEBG0@Z; RegistrationGuard::IsGuarded(ushort const *,ushort const *)
0x180011ff2  test    al, al
0x180011ff4  jz      short loc_180011FFD
0x180011ff6  xor     eax, eax
0x180011ff8  jmp     loc_1800121E2
0x180011ffd  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x180012002  test    rax, rax
0x180012005  jnz     short loc_180012011
0x180012007  mov     eax, 8000FFFFh
0x18001200c  jmp     loc_1800121E2
0x180012011  mov     [rsp+348h+var_308], r15
0x180012016  lea     rdx, [rsp+348h+var_308]
0x18001201b  mov     rcx, rbx
0x18001201e  call    ?CreateStream@StringReader@@SAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@@Z; StringReader::CreateStream(ushort const *,_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> &)
0x180012023  mov     [rsp+348h+var_318], eax
0x180012027  test    eax, eax
0x180012029  jns     short loc_180012070
0x18001202b  mov     [rsp+348h+var_2F8], r15b
0x180012030  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012037  mov     [rsp+348h+pExceptionObject], rcx
0x18001203c  lea     rcx, byte_1800505F8
0x180012043  mov     [rsp+348h+var_2F0], rcx
0x180012048  mov     [rsp+348h+var_2E8], r15
0x18001204d  mov     [rsp+348h+var_2E0], r15
0x180012052  mov     [rsp+348h+var_2D8], eax
0x180012056  mov     [rsp+348h+var_2D4], 0FFFFFFFFFFFFFFFFh
0x18001205f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012066  lea     rcx, [rsp+348h+pExceptionObject]; pExceptionObject
0x18001206b  call    _CxxThrowException_0
0x180012070  mov     [rsp+348h+var_310], r15
0x180012075  mov     ecx, 460h; Size
0x18001207a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001207f  test    rax, rax
0x180012082  jz      short loc_18001209F
0x180012084  lea     rdx, [rsp+348h+var_308]
0x180012089  mov     rcx, rax
0x18001208c  call    ??0TaskXmlReader@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@PEAPEAE_N@Z; TaskXmlReader::TaskXmlReader(_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> const &,uchar * *,bool)
0x180012091  mov     rbx, rax
0x180012094  test    rax, rax
0x180012097  jz      short loc_1800120A2
0x180012099  lock inc dword ptr [rax+8]
0x18001209d  jmp     short loc_1800120A2
0x18001209f  mov     rbx, r15
0x1800120a2  lea     rcx, [rsp+348h+var_310]
0x1800120a7  call    ??1?$AutoRef@VRpcSession@@@wmi@@QEAA@XZ; wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(void)
0x1800120ac  mov     [rsp+348h+var_310], rbx
0x1800120b1  test    rbx, rbx
0x1800120b4  jnz     short loc_180012117
0x1800120b6  mov     [rsp+348h+var_2C0], r15b
0x1800120be  lea     rcx, byte_1800505F8
0x1800120c5  mov     [rsp+348h+var_2B8], rcx
0x1800120cd  mov     [rsp+348h+var_2B0], r15
0x1800120d5  mov     [rsp+348h+var_2A8], r15
0x1800120dd  mov     [rsp+348h+var_2A0], 0Eh
0x1800120e8  mov     [rsp+348h+var_29C], 0FFFFFFFFFFFFFFFFh
0x1800120f4  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x1800120fb  mov     [rsp+348h+var_2C8], rax
0x180012103  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x18001210a  lea     rcx, [rsp+348h+var_2C8]; pExceptionObject
0x180012112  call    _CxxThrowException_0
0x180012117  mov     r9d, esi; unsigned int
0x18001211a  mov     r8, r14; unsigned __int16 *
0x18001211d  mov     rdx, rdi; unsigned __int16 *
0x180012120  lea     rcx, [rsp+348h+var_248]; this
0x180012128  call    ??0BinXmlHandler@@QEAA@PEBGPEAGK@Z; BinXmlHandler::BinXmlHandler(ushort const *,ushort *,ulong)
0x18001212d  nop
0x18001212e  lea     rdx, [rsp+348h+var_248]; struct ITaskXmlHandler *
0x180012136  mov     rcx, rbx; this
0x180012139  call    ?ProcessXml@TaskXmlReader@@QEAAJPEAUITaskXmlHandler@@@Z; TaskXmlReader::ProcessXml(ITaskXmlHandler *)
0x18001213e  mov     [rsp+348h+var_318], eax
0x180012142  test    eax, eax
0x180012144  jns     short loc_1800121A3
0x180012146  mov     [rsp+348h+var_288], r15b
0x18001214e  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012155  mov     [rsp+348h+var_290], rcx
0x18001215d  lea     rcx, byte_1800505F8
0x180012164  mov     [rsp+348h+var_280], rcx
0x18001216c  mov     [rsp+348h+var_278], r15
0x180012174  mov     [rsp+348h+var_270], r15
0x18001217c  mov     [rsp+348h+var_268], eax
0x180012183  mov     [rsp+348h+var_264], 0FFFFFFFFFFFFFFFFh
0x18001218f  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012196  lea     rcx, [rsp+348h+var_290]; pExceptionObject
0x18001219e  call    _CxxThrowException_0
0x1800121a3  lea     rcx, [rsp+348h+var_248]; this
0x1800121ab  call    ?SaveLegacyTask@BinXmlHandler@@QEAAJXZ; BinXmlHandler::SaveLegacyTask(void)
0x1800121b0  mov     ebx, eax
0x1800121b2  mov     [rsp+348h+var_318], eax
0x1800121b6  lea     rcx, [rsp+348h+var_248]; this
0x1800121be  call    ??1BinXmlHandler@@QEAA@XZ; BinXmlHandler::~BinXmlHandler(void)
0x1800121c3  nop
0x1800121c4  lea     rcx, [rsp+348h+var_310]
0x1800121c9  call    ??1?$AutoRef@VRpcSession@@@wmi@@QEAA@XZ; wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(void)
0x1800121ce  nop
0x1800121cf  lea     rcx, [rsp+348h+var_308]
0x1800121d4  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800121d9  nop
0x1800121da  jmp     short loc_1800121E0
0x1800121dc  mov     ebx, [rsp+348h+var_318]
0x1800121e0  mov     eax, ebx
0x1800121e2  mov     rcx, [rsp+348h+var_28]
0x1800121ea  xor     rcx, rsp; StackCookie
0x1800121ed  call    __security_check_cookie
0x1800121f2  lea     r11, [rsp+348h+var_18]
0x1800121fa  mov     rbx, [r11+30h]
0x1800121fe  mov     rsi, [r11+38h]
0x180012202  mov     rsp, r11
0x180012205  pop     r15
0x180012207  pop     r14
0x180012209  pop     rdi
0x18001220a  retn
```

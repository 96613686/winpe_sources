# RegisterTaskNotification(ushort const *,ushort const *,ushort const *,ulong,ushort *)

- ea: `0x180012a70`
- end: `0x180012d42`
- name: `?RegisterTaskNotification@@YAJPEBG00KPEAG@Z`
- size: `722`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005c10`
- `0x180007948`
- `0x180008c4c`
- `0x18000a15c`
- `0x18000a230`
- `0x18000a274`
- `0x18000d128`
- `0x18000dca8`
- `0x180010768`
- `0x180010d74`
- `0x180011f10`
- `0x180012a70`
- `0x18001d634`
- `0x180021710`
- `0x180030700`

## import_xrefs

- `msvcrt!wcschr` at `0x180012b02`
- `msvcrt!wcschr` at `0x180012b02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
    v20 = byte_180052608;
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
    v27 = byte_180052608;
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
    v34 = byte_180052608;
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
0x180012a70  mov     [rsp+arg_10], rbx
0x180012a75  mov     [rsp+arg_18], rsi
0x180012a7a  push    rdi
0x180012a7b  push    r14
0x180012a7d  push    r15
0x180012a7f  sub     rsp, 330h
0x180012a86  mov     rax, cs:__security_cookie
0x180012a8d  xor     rax, rsp
0x180012a90  mov     [rsp+348h+var_28], rax
0x180012a98  mov     esi, r9d
0x180012a9b  mov     rbx, rdx
0x180012a9e  mov     rdi, rcx
0x180012aa1  mov     r14, [rsp+348h+arg_20]
0x180012aa9  xor     r15d, r15d
0x180012aac  mov     [rsp+348h+var_318], r15d
0x180012ab1  lea     rax, WPP_GLOBAL_Control
0x180012ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180012abf  cmp     rcx, rax
0x180012ac2  jz      short loc_180012AE7
0x180012ac4  test    byte ptr [rcx+1Ch], 2
0x180012ac8  jz      short loc_180012AE7
0x180012aca  cmp     byte ptr [rcx+19h], 4
0x180012ace  jb      short loc_180012AE7
0x180012ad0  lea     edx, [r15+28h]
0x180012ad4  mov     r9, rdi
0x180012ad7  lea     r8, WPP_6ec190dc111e3f5177d44fecd15f7dcf_Traceguids
0x180012ade  mov     rcx, [rcx+10h]
0x180012ae2  call    WPP_SF_S
0x180012ae7  test    rdi, rdi
0x180012aea  jz      short loc_180012B1D
0x180012aec  lea     rax, [rdi+2]
0x180012af0  mov     edx, 5Ch ; '\'; Ch
0x180012af5  cmp     [rdi], dx
0x180012af8  cmovnz  rax, rdi
0x180012afc  mov     rdi, rax
0x180012aff  mov     rcx, rax; Str
0x180012b02  call    cs:__imp_wcschr
0x180012b09  nop     dword ptr [rax+rax+00h]
0x180012b0e  test    rax, rax
0x180012b11  jz      short loc_180012B1D
0x180012b13  mov     eax, 1
0x180012b18  jmp     loc_180012D18
0x180012b1d  mov     rdx, rbx; unsigned __int16 *
0x180012b20  mov     rcx, rdi; unsigned __int16 *
0x180012b23  call    ?IsGuarded@RegistrationGuard@@SA_NPEBG0@Z; RegistrationGuard::IsGuarded(ushort const *,ushort const *)
0x180012b28  test    al, al
0x180012b2a  jz      short loc_180012B33
0x180012b2c  xor     eax, eax
0x180012b2e  jmp     loc_180012D18
0x180012b33  call    ?GetAdapter@CompatibilityAdapter@@SAPEAV1@XZ; CompatibilityAdapter::GetAdapter(void)
0x180012b38  test    rax, rax
0x180012b3b  jnz     short loc_180012B47
0x180012b3d  mov     eax, 8000FFFFh
0x180012b42  jmp     loc_180012D18
0x180012b47  mov     [rsp+348h+var_308], r15
0x180012b4c  lea     rdx, [rsp+348h+var_308]
0x180012b51  mov     rcx, rbx
0x180012b54  call    ?CreateStream@StringReader@@SAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@@Z; StringReader::CreateStream(ushort const *,_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> &)
0x180012b59  mov     [rsp+348h+var_318], eax
0x180012b5d  test    eax, eax
0x180012b5f  jns     short loc_180012BA6
0x180012b61  mov     [rsp+348h+var_2F8], r15b
0x180012b66  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012b6d  mov     [rsp+348h+pExceptionObject], rcx
0x180012b72  lea     rcx, byte_180052608
0x180012b79  mov     [rsp+348h+var_2F0], rcx
0x180012b7e  mov     [rsp+348h+var_2E8], r15
0x180012b83  mov     [rsp+348h+var_2E0], r15
0x180012b88  mov     [rsp+348h+var_2D8], eax
0x180012b8c  mov     [rsp+348h+var_2D4], 0FFFFFFFFFFFFFFFFh
0x180012b95  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012b9c  lea     rcx, [rsp+348h+pExceptionObject]; pExceptionObject
0x180012ba1  call    _CxxThrowException_0
0x180012ba6  mov     [rsp+348h+var_310], r15
0x180012bab  mov     ecx, 460h; Size
0x180012bb0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012bb5  test    rax, rax
0x180012bb8  jz      short loc_180012BD5
0x180012bba  lea     rdx, [rsp+348h+var_308]
0x180012bbf  mov     rcx, rax
0x180012bc2  call    ??0TaskXmlReader@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@PEAPEAE_N@Z; TaskXmlReader::TaskXmlReader(_com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>> const &,uchar * *,bool)
0x180012bc7  mov     rbx, rax
0x180012bca  test    rax, rax
0x180012bcd  jz      short loc_180012BD8
0x180012bcf  lock inc dword ptr [rax+8]
0x180012bd3  jmp     short loc_180012BD8
0x180012bd5  mov     rbx, r15
0x180012bd8  lea     rcx, [rsp+348h+var_310]
0x180012bdd  call    ??1?$AutoRef@VRpcSession@@@wmi@@QEAA@XZ; wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(void)
0x180012be2  mov     [rsp+348h+var_310], rbx
0x180012be7  test    rbx, rbx
0x180012bea  jnz     short loc_180012C4D
0x180012bec  mov     [rsp+348h+var_2C0], r15b
0x180012bf4  lea     rcx, byte_180052608
0x180012bfb  mov     [rsp+348h+var_2B8], rcx
0x180012c03  mov     [rsp+348h+var_2B0], r15
0x180012c0b  mov     [rsp+348h+var_2A8], r15
0x180012c13  mov     [rsp+348h+var_2A0], 0Eh
0x180012c1e  mov     [rsp+348h+var_29C], 0FFFFFFFFFFFFFFFFh
0x180012c2a  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012c31  mov     [rsp+348h+var_2C8], rax
0x180012c39  lea     rdx, _TI4?AVOutOfMemoryException@wmi@@; pThrowInfo
0x180012c40  lea     rcx, [rsp+348h+var_2C8]; pExceptionObject
0x180012c48  call    _CxxThrowException_0
0x180012c4d  mov     r9d, esi; unsigned int
0x180012c50  mov     r8, r14; unsigned __int16 *
0x180012c53  mov     rdx, rdi; unsigned __int16 *
0x180012c56  lea     rcx, [rsp+348h+var_248]; this
0x180012c5e  call    ??0BinXmlHandler@@QEAA@PEBGPEAGK@Z; BinXmlHandler::BinXmlHandler(ushort const *,ushort *,ulong)
0x180012c63  nop
0x180012c64  lea     rdx, [rsp+348h+var_248]; struct ITaskXmlHandler *
0x180012c6c  mov     rcx, rbx; this
0x180012c6f  call    ?ProcessXml@TaskXmlReader@@QEAAJPEAUITaskXmlHandler@@@Z; TaskXmlReader::ProcessXml(ITaskXmlHandler *)
0x180012c74  mov     [rsp+348h+var_318], eax
0x180012c78  test    eax, eax
0x180012c7a  jns     short loc_180012CD9
0x180012c7c  mov     [rsp+348h+var_288], r15b
0x180012c84  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180012c8b  mov     [rsp+348h+var_290], rcx
0x180012c93  lea     rcx, byte_180052608
0x180012c9a  mov     [rsp+348h+var_280], rcx
0x180012ca2  mov     [rsp+348h+var_278], r15
0x180012caa  mov     [rsp+348h+var_270], r15
0x180012cb2  mov     [rsp+348h+var_268], eax
0x180012cb9  mov     [rsp+348h+var_264], 0FFFFFFFFFFFFFFFFh
0x180012cc5  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180012ccc  lea     rcx, [rsp+348h+var_290]; pExceptionObject
0x180012cd4  call    _CxxThrowException_0
0x180012cd9  lea     rcx, [rsp+348h+var_248]; this
0x180012ce1  call    ?SaveLegacyTask@BinXmlHandler@@QEAAJXZ; BinXmlHandler::SaveLegacyTask(void)
0x180012ce6  mov     ebx, eax
0x180012ce8  mov     [rsp+348h+var_318], eax
0x180012cec  lea     rcx, [rsp+348h+var_248]; this
0x180012cf4  call    ??1BinXmlHandler@@QEAA@XZ; BinXmlHandler::~BinXmlHandler(void)
0x180012cf9  nop
0x180012cfa  lea     rcx, [rsp+348h+var_310]
0x180012cff  call    ??1?$AutoRef@VRpcSession@@@wmi@@QEAA@XZ; wmi::AutoRef<RpcSession>::~AutoRef<RpcSession>(void)
0x180012d04  nop
0x180012d05  lea     rcx, [rsp+348h+var_308]
0x180012d0a  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x180012d0f  nop
0x180012d10  jmp     short loc_180012D16
0x180012d12  mov     ebx, [rsp+348h+var_318]
0x180012d16  mov     eax, ebx
0x180012d18  mov     rcx, [rsp+348h+var_28]
0x180012d20  xor     rcx, rsp; StackCookie
0x180012d23  call    __security_check_cookie
0x180012d28  lea     r11, [rsp+348h+var_18]
0x180012d30  mov     rbx, [r11+30h]
0x180012d34  mov     rsi, [r11+38h]
0x180012d38  mov     rsp, r11
0x180012d3b  pop     r15
0x180012d3d  pop     r14
0x180012d3f  pop     rdi
0x180012d40  retn
```

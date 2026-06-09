# COMXProc::CHardwareDevicesMountPointsEnumImpl::Next(ushort * *,ushort * *)

- ea: `0x180029a20`
- end: `0x180029b59`
- name: `?Next@CHardwareDevicesMountPointsEnumImpl@COMXProc@@UEAAJPEAPEAG0@Z`
- size: `313`
- prototype: `__int64 __fastcall(COMXProc::CHardwareDevicesMountPointsEnumImpl *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180003570`
- `0x1800140f0`
- `0x1800176e8`
- `0x180019598`
- `0x1800235a8`
- `0x1800280cc`
- `0x180029a20`
- `0x180032b38`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029b11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029b11`

## pseudocode

```c
__int64 __fastcall COMXProc::CHardwareDevicesMountPointsEnumImpl::Next(
        COMXProc::CHardwareDevicesMountPointsEnumImpl *this,
        LPVOID *a2,
        unsigned __int16 **a3)
{
  int v6; // eax
  int Name; // ebx
  XProcHelpers *v8; // rcx
  int v9; // eax
  CNamedElemHelper *v10; // rsi
  unsigned int v12; // [rsp+20h] [rbp-458h] BYREF
  CNamedElemHelper *v13; // [rsp+28h] [rbp-450h] BYREF
  unsigned __int16 Src[264]; // [rsp+30h] [rbp-448h] BYREF
  unsigned __int16 v15[264]; // [rsp+240h] [rbp-238h] BYREF

  v6 = XProcHelpers::XProcFunctionCallEnter(1);
  *a2 = 0;
  Name = v6;
  *a3 = 0;
  if ( v6 >= 0 )
  {
    v8 = (XProcHelpers *)*((_QWORD *)this + 1);
    if ( v8 )
    {
      v13 = 0;
      v9 = CNamedElemEnum<Storage::CDisk>::Next(v8, &v13);
      Name = v9;
      if ( v9 >= 0 && v9 != 1 )
      {
        v10 = v13;
        v12 = 0;
        Name = CNamedElemHelper::GetName(v13, Src, 0x104u, &v12);
        if ( Name >= 0 )
        {
          Name = StringCchCopyW(v15, 0x104u, (const unsigned __int16 *)v10 + 16);
          if ( Name >= 0 )
          {
            Name = DupOleString(Src);
            if ( Name < 0 )
            {
              CoTaskMemFree(*a2);
              *a2 = 0;
            }
            else
            {
              Name = DupOleString(v15);
            }
          }
        }
        CRefCounted::Release((CNamedElemHelper *)((char *)v10 + 16));
      }
    }
    else
    {
      Name = 1;
    }
    XProcHelpers::XProcFunctionCallExit(v8);
  }
  return (unsigned int)Name;
}

```

## disassembly

```asm
0x180029a20  mov     [rsp+arg_18], rbx
0x180029a25  push    rsi
0x180029a26  push    rdi
0x180029a27  push    r14
0x180029a29  sub     rsp, 460h
0x180029a30  mov     rax, cs:__security_cookie
0x180029a37  xor     rax, rsp
0x180029a3a  mov     [rsp+478h+var_28], rax
0x180029a42  mov     rsi, rcx
0x180029a45  mov     r14, r8
0x180029a48  mov     ecx, 1
0x180029a4d  mov     rdi, rdx
0x180029a50  call    ?XProcFunctionCallEnter@XProcHelpers@@YAJW4XPROC_ENTER_BEHAVIOR@@@Z; XProcHelpers::XProcFunctionCallEnter(XPROC_ENTER_BEHAVIOR)
0x180029a55  mov     qword ptr [rdi], 0
0x180029a5c  mov     ebx, eax
0x180029a5e  mov     qword ptr [r14], 0
0x180029a65  test    eax, eax
0x180029a67  js      loc_180029B33
0x180029a6d  mov     rcx, [rsi+8]; this
0x180029a71  test    rcx, rcx
0x180029a74  jz      loc_180029B29
0x180029a7a  lea     rdx, [rsp+478h+var_450]
0x180029a7f  mov     [rsp+478h+var_450], 0
0x180029a88  call    ?Next@?$CNamedElemEnum@VCDisk@Storage@@@@QEAAJPEAPEAVCDisk@Storage@@@Z; CNamedElemEnum<Storage::CDisk>::Next(Storage::CDisk * *)
0x180029a8d  mov     ebx, eax
0x180029a8f  test    eax, eax
0x180029a91  js      loc_180029B2E
0x180029a97  cmp     eax, 1
0x180029a9a  jz      loc_180029B2E
0x180029aa0  mov     rsi, [rsp+478h+var_450]
0x180029aa5  lea     r9, [rsp+478h+var_458]; unsigned int *
0x180029aaa  mov     rcx, rsi; this
0x180029aad  mov     [rsp+478h+var_458], 0
0x180029ab5  mov     r8d, 104h; unsigned int
0x180029abb  lea     rdx, [rsp+478h+Src]; unsigned __int16 *
0x180029ac0  call    ?GetName@CNamedElemHelper@@QEAAJPEAGKPEAK@Z; CNamedElemHelper::GetName(ushort *,ulong,ulong *)
0x180029ac5  mov     ebx, eax
0x180029ac7  test    eax, eax
0x180029ac9  js      short loc_180029B1E
0x180029acb  lea     r8, [rsi+20h]; unsigned __int16 *
0x180029acf  mov     edx, 104h; unsigned __int64
0x180029ad4  lea     rcx, [rsp+478h+var_238]; unsigned __int16 *
0x180029adc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029ae1  mov     ebx, eax
0x180029ae3  test    eax, eax
0x180029ae5  js      short loc_180029B1E
0x180029ae7  mov     rdx, rdi
0x180029aea  lea     rcx, [rsp+478h+Src]; Src
0x180029aef  call    DupOleString
0x180029af4  mov     ebx, eax
0x180029af6  test    eax, eax
0x180029af8  js      short loc_180029B0E
0x180029afa  mov     rdx, r14
0x180029afd  lea     rcx, [rsp+478h+var_238]; Src
0x180029b05  call    DupOleString
0x180029b0a  mov     ebx, eax
0x180029b0c  jmp     short loc_180029B1E
0x180029b0e  mov     rcx, [rdi]; pv
0x180029b11  call    cs:__imp_CoTaskMemFree
0x180029b17  mov     qword ptr [rdi], 0
0x180029b1e  lea     rcx, [rsi+10h]; this
0x180029b22  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180029b27  jmp     short loc_180029B2E
0x180029b29  mov     ebx, 1
0x180029b2e  call    ?XProcFunctionCallExit@XProcHelpers@@YAJXZ; XProcHelpers::XProcFunctionCallExit(void)
0x180029b33  mov     eax, ebx
0x180029b35  mov     rcx, [rsp+478h+var_28]
0x180029b3d  xor     rcx, rsp; StackCookie
0x180029b40  call    __security_check_cookie
0x180029b45  mov     rbx, [rsp+478h+arg_18]
0x180029b4d  add     rsp, 460h
0x180029b54  pop     r14
0x180029b56  pop     rdi
0x180029b57  pop     rsi
0x180029b58  retn
```

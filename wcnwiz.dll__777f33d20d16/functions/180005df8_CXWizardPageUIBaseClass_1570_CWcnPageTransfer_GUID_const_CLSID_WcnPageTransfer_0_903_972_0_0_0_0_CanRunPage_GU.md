# CXWizardPageUIBaseClass<1570,CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,0,903,972,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005df8`
- end: `0x180005f18`
- name: `?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageTransfer@@$1?CLSID_WcnPageTransfer@@3U_GUID@@B$0A@$0DIH@$0DMM@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800051b0`

## callees

- `0x180002294`
- `0x180005740`
- `0x180005df8`
- `0x18002f81c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005e6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005e6c`

## pseudocode

```c
__int64 __fastcall CXWizardPageUIBaseClass<1570,CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,0,903,972,0,0,0,0>::CanRunPage(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        __int64 a6,
        int a7,
        struct IXWizardSource *a8,
        _QWORD *a9)
{
  __int16 v9; // bx
  __int64 result; // rax
  char *v12; // rax
  char *v13; // rbx

  v9 = a4;
  result = CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7,
             a8,
             (__int64)a9);
  if ( (int)result >= 0 )
  {
    if ( (v9 & 0x622) != 0 )
    {
      v12 = (char *)CoTaskMemAlloc(0x68u);
      v13 = v12;
      if ( v12 )
      {
        memset_0(v12 + 8, 0, 0x60u);
        *(_DWORD *)v13 = 104;
        *((_DWORD *)v13 + 1) = 12300;
        *((_QWORD *)v13 + 1) = hModule;
        *((_QWORD *)v13 + 6) = _RTDynamicCast_0(
                                 a1,
                                 0,
                                 &CXWizardPageUIBaseClass<1570,CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,0,903,972,0,0,0,0> `RTTI Type Descriptor',
                                 &CWcnPageTransfer `RTTI Type Descriptor',
                                 0);
        *((_QWORD *)v13 + 5) = CXWizardPageUIBaseClass<1570,CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,0,903,972,0,0,0,0>::PageDlgProcRoot;
        result = 0;
        *((_QWORD *)v13 + 2) = 903;
        *((_QWORD *)v13 + 9) = 972;
        *((_QWORD *)v13 + 10) = 0;
        *((_QWORD *)v13 + 4) = 0;
        *((_QWORD *)v13 + 3) = 0;
        *a9 = v13;
      }
      else
      {
        return 2147942414LL;
      }
    }
    else
    {
      return 2147500033LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005df8  mov     r11, rsp
0x180005dfb  mov     [r11+8], rbx
0x180005dff  mov     [r11+10h], rsi
0x180005e03  push    rdi
0x180005e04  sub     rsp, 50h
0x180005e08  mov     rax, [rsp+58h+arg_38]
0x180005e10  mov     ebx, r9d
0x180005e13  mov     rsi, [rsp+58h+arg_40]
0x180005e1b  mov     rdi, rcx
0x180005e1e  mov     [r11-18h], rsi
0x180005e22  mov     [r11-20h], rax
0x180005e26  mov     eax, [rsp+58h+arg_30]
0x180005e2d  mov     [rsp+58h+var_28], eax; int
0x180005e31  mov     rax, [rsp+58h+arg_28]
0x180005e39  mov     [r11-30h], rax
0x180005e3d  mov     eax, [rsp+58h+arg_20]
0x180005e44  mov     [rsp+58h+var_38], eax; int
0x180005e48  call    ?CanRunPage@?$CXWizardPageClass@VCWcnPageAuthNonUi@@$1?CLSID_WcnPageAuthNonUi@@3U_GUID@@B$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005e4d  test    eax, eax
0x180005e4f  js      loc_180005F08
0x180005e55  test    ebx, 622h
0x180005e5b  jnz     short loc_180005E67
0x180005e5d  mov     eax, 80004001h
0x180005e62  jmp     loc_180005F08
0x180005e67  mov     ecx, 68h ; 'h'; cb
0x180005e6c  call    cs:__imp_CoTaskMemAlloc
0x180005e72  mov     rbx, rax
0x180005e75  test    rax, rax
0x180005e78  jz      loc_180005F03
0x180005e7e  xor     edx, edx; Val
0x180005e80  lea     rcx, [rax+8]; void *
0x180005e84  lea     r8d, [rdx+60h]; Size
0x180005e88  call    memset_0
0x180005e8d  mov     dword ptr [rbx], 68h ; 'h'
0x180005e93  lea     r9, ??_R0?AVCWcnPageTransfer@@@8; CWcnPageTransfer `RTTI Type Descriptor'
0x180005e9a  mov     dword ptr [rbx+4], 300Ch
0x180005ea1  lea     r8, ??_R0?AV?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageTransfer@@$1?CLSID_WcnPageTransfer@@3U_GUID@@B$0A@$0DIH@$0DMM@$0A@$0A@$0A@$0A@@@@8; CXWizardPageUIBaseClass<1570,CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,0,903,972,0,0,0,0> `RTTI Type Descriptor'
0x180005ea8  mov     rcx, cs:hModule
0x180005eaf  xor     edx, edx
0x180005eb1  mov     [rbx+8], rcx
0x180005eb5  mov     rcx, rdi
0x180005eb8  mov     [rsp+58h+var_38], 0
0x180005ec0  call    __RTDynamicCast_0
0x180005ec5  mov     [rbx+30h], rax
0x180005ec9  lea     rax, ?PageDlgProcRoot@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageTransfer@@$1?CLSID_WcnPageTransfer@@3U_GUID@@B$0A@$0DIH@$0DMM@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardPageUIBaseClass<1570,CWcnPageTransfer,&_GUID const CLSID_WcnPageTransfer,0,903,972,0,0,0,0>::PageDlgProcRoot(HWND__ *,uint,unsigned __int64,__int64)
0x180005ed0  mov     [rbx+28h], rax
0x180005ed4  xor     eax, eax
0x180005ed6  mov     qword ptr [rbx+10h], 387h
0x180005ede  mov     qword ptr [rbx+48h], 3CCh
0x180005ee6  mov     qword ptr [rbx+50h], 0
0x180005eee  mov     qword ptr [rbx+20h], 0
0x180005ef6  mov     qword ptr [rbx+18h], 0
0x180005efe  mov     [rsi], rbx
0x180005f01  jmp     short loc_180005F08
0x180005f03  mov     eax, 8007000Eh
0x180005f08  mov     rbx, [rsp+58h+arg_0]
0x180005f0d  mov     rsi, [rsp+58h+arg_8]
0x180005f12  add     rsp, 50h
0x180005f16  pop     rdi
0x180005f17  retn
```

# CXWizardPageUIBaseClass<1570,CWcnPageTransferFailed,&_GUID const CLSID_WcnPageTransferFailed,0,521,3312,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005f20`
- end: `0x180006040`
- name: `?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageTransferFailed@@$1?CLSID_WcnPageTransferFailed@@3U_GUID@@B$0A@$0CAJ@$0MPA@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005270`

## callees

- `0x180002294`
- `0x180005740`
- `0x180005f20`
- `0x18002f81c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005f94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005f94`

## pseudocode

```c
__int64 __fastcall CXWizardPageUIBaseClass<1570,CWcnPageTransferFailed,&_GUID const CLSID_WcnPageTransferFailed,0,521,3312,0,0,0,0>::CanRunPage(
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
                                 &CXWizardPageUIBaseClass<1570,CWcnPageTransferFailed,&_GUID const CLSID_WcnPageTransferFailed,0,521,3312,0,0,0,0> `RTTI Type Descriptor',
                                 &CWcnPageTransferFailed `RTTI Type Descriptor',
                                 0);
        *((_QWORD *)v13 + 5) = CXWizardPageUIBaseClass<1570,CWcnPageTransferFailed,&_GUID const CLSID_WcnPageTransferFailed,0,521,3312,0,0,0,0>::PageDlgProcRoot;
        result = 0;
        *((_QWORD *)v13 + 2) = 521;
        *((_QWORD *)v13 + 9) = 3312;
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
0x180005f20  mov     r11, rsp
0x180005f23  mov     [r11+8], rbx
0x180005f27  mov     [r11+10h], rsi
0x180005f2b  push    rdi
0x180005f2c  sub     rsp, 50h
0x180005f30  mov     rax, [rsp+58h+arg_38]
0x180005f38  mov     ebx, r9d
0x180005f3b  mov     rsi, [rsp+58h+arg_40]
0x180005f43  mov     rdi, rcx
0x180005f46  mov     [r11-18h], rsi
0x180005f4a  mov     [r11-20h], rax
0x180005f4e  mov     eax, [rsp+58h+arg_30]
0x180005f55  mov     [rsp+58h+var_28], eax; int
0x180005f59  mov     rax, [rsp+58h+arg_28]
0x180005f61  mov     [r11-30h], rax
0x180005f65  mov     eax, [rsp+58h+arg_20]
0x180005f6c  mov     [rsp+58h+var_38], eax; int
0x180005f70  call    ?CanRunPage@?$CXWizardPageClass@VCWcnPageAuthNonUi@@$1?CLSID_WcnPageAuthNonUi@@3U_GUID@@B$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005f75  test    eax, eax
0x180005f77  js      loc_180006030
0x180005f7d  test    ebx, 622h
0x180005f83  jnz     short loc_180005F8F
0x180005f85  mov     eax, 80004001h
0x180005f8a  jmp     loc_180006030
0x180005f8f  mov     ecx, 68h ; 'h'; cb
0x180005f94  call    cs:__imp_CoTaskMemAlloc
0x180005f9a  mov     rbx, rax
0x180005f9d  test    rax, rax
0x180005fa0  jz      loc_18000602B
0x180005fa6  xor     edx, edx; Val
0x180005fa8  lea     rcx, [rax+8]; void *
0x180005fac  lea     r8d, [rdx+60h]; Size
0x180005fb0  call    memset_0
0x180005fb5  mov     dword ptr [rbx], 68h ; 'h'
0x180005fbb  lea     r9, ??_R0?AVCWcnPageTransferFailed@@@8; CWcnPageTransferFailed `RTTI Type Descriptor'
0x180005fc2  mov     dword ptr [rbx+4], 300Ch
0x180005fc9  lea     r8, ??_R0?AV?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageTransferFailed@@$1?CLSID_WcnPageTransferFailed@@3U_GUID@@B$0A@$0CAJ@$0MPA@$0A@$0A@$0A@$0A@@@@8; CXWizardPageUIBaseClass<1570,CWcnPageTransferFailed,&_GUID const CLSID_WcnPageTransferFailed,0,521,3312,0,0,0,0> `RTTI Type Descriptor'
0x180005fd0  mov     rcx, cs:hModule
0x180005fd7  xor     edx, edx
0x180005fd9  mov     [rbx+8], rcx
0x180005fdd  mov     rcx, rdi
0x180005fe0  mov     [rsp+58h+var_38], 0
0x180005fe8  call    __RTDynamicCast_0
0x180005fed  mov     [rbx+30h], rax
0x180005ff1  lea     rax, ?PageDlgProcRoot@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageTransferFailed@@$1?CLSID_WcnPageTransferFailed@@3U_GUID@@B$0A@$0CAJ@$0MPA@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardPageUIBaseClass<1570,CWcnPageTransferFailed,&_GUID const CLSID_WcnPageTransferFailed,0,521,3312,0,0,0,0>::PageDlgProcRoot(HWND__ *,uint,unsigned __int64,__int64)
0x180005ff8  mov     [rbx+28h], rax
0x180005ffc  xor     eax, eax
0x180005ffe  mov     qword ptr [rbx+10h], 209h
0x180006006  mov     qword ptr [rbx+48h], 0CF0h
0x18000600e  mov     qword ptr [rbx+50h], 0
0x180006016  mov     qword ptr [rbx+20h], 0
0x18000601e  mov     qword ptr [rbx+18h], 0
0x180006026  mov     [rsi], rbx
0x180006029  jmp     short loc_180006030
0x18000602b  mov     eax, 8007000Eh
0x180006030  mov     rbx, [rsp+58h+arg_0]
0x180006035  mov     rsi, [rsp+58h+arg_8]
0x18000603a  add     rsp, 50h
0x18000603e  pop     rdi
0x18000603f  retn
```

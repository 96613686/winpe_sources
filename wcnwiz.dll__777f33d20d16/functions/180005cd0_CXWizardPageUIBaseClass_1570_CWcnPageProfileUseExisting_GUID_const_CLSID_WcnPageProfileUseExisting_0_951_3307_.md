# CXWizardPageUIBaseClass<1570,CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0,951,3307,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005cd0`
- end: `0x180005df0`
- name: `?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageProfileUseExisting@@$1?CLSID_WcnPageProfileUseExisting@@3U_GUID@@B$0A@$0DLH@$0MOL@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800050f0`

## callees

- `0x180002294`
- `0x180005740`
- `0x180005cd0`
- `0x18002f81c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005d44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005d44`

## pseudocode

```c
__int64 __fastcall CXWizardPageUIBaseClass<1570,CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0,951,3307,0,0,0,0>::CanRunPage(
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
                                 &CXWizardPageUIBaseClass<1570,CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0,951,3307,0,0,0,0> `RTTI Type Descriptor',
                                 &CWcnPageProfileUseExisting `RTTI Type Descriptor',
                                 0);
        *((_QWORD *)v13 + 5) = CXWizardPageUIBaseClass<1570,CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0,951,3307,0,0,0,0>::PageDlgProcRoot;
        result = 0;
        *((_QWORD *)v13 + 2) = 951;
        *((_QWORD *)v13 + 9) = 3307;
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
0x180005cd0  mov     r11, rsp
0x180005cd3  mov     [r11+8], rbx
0x180005cd7  mov     [r11+10h], rsi
0x180005cdb  push    rdi
0x180005cdc  sub     rsp, 50h
0x180005ce0  mov     rax, [rsp+58h+arg_38]
0x180005ce8  mov     ebx, r9d
0x180005ceb  mov     rsi, [rsp+58h+arg_40]
0x180005cf3  mov     rdi, rcx
0x180005cf6  mov     [r11-18h], rsi
0x180005cfa  mov     [r11-20h], rax
0x180005cfe  mov     eax, [rsp+58h+arg_30]
0x180005d05  mov     [rsp+58h+var_28], eax; int
0x180005d09  mov     rax, [rsp+58h+arg_28]
0x180005d11  mov     [r11-30h], rax
0x180005d15  mov     eax, [rsp+58h+arg_20]
0x180005d1c  mov     [rsp+58h+var_38], eax; int
0x180005d20  call    ?CanRunPage@?$CXWizardPageClass@VCWcnPageAuthNonUi@@$1?CLSID_WcnPageAuthNonUi@@3U_GUID@@B$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005d25  test    eax, eax
0x180005d27  js      loc_180005DE0
0x180005d2d  test    ebx, 622h
0x180005d33  jnz     short loc_180005D3F
0x180005d35  mov     eax, 80004001h
0x180005d3a  jmp     loc_180005DE0
0x180005d3f  mov     ecx, 68h ; 'h'; cb
0x180005d44  call    cs:__imp_CoTaskMemAlloc
0x180005d4a  mov     rbx, rax
0x180005d4d  test    rax, rax
0x180005d50  jz      loc_180005DDB
0x180005d56  xor     edx, edx; Val
0x180005d58  lea     rcx, [rax+8]; void *
0x180005d5c  lea     r8d, [rdx+60h]; Size
0x180005d60  call    memset_0
0x180005d65  mov     dword ptr [rbx], 68h ; 'h'
0x180005d6b  lea     r9, ??_R0?AVCWcnPageProfileUseExisting@@@8; CWcnPageProfileUseExisting `RTTI Type Descriptor'
0x180005d72  mov     dword ptr [rbx+4], 300Ch
0x180005d79  lea     r8, ??_R0?AV?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageProfileUseExisting@@$1?CLSID_WcnPageProfileUseExisting@@3U_GUID@@B$0A@$0DLH@$0MOL@$0A@$0A@$0A@$0A@@@@8; CXWizardPageUIBaseClass<1570,CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0,951,3307,0,0,0,0> `RTTI Type Descriptor'
0x180005d80  mov     rcx, cs:hModule
0x180005d87  xor     edx, edx
0x180005d89  mov     [rbx+8], rcx
0x180005d8d  mov     rcx, rdi
0x180005d90  mov     [rsp+58h+var_38], 0
0x180005d98  call    __RTDynamicCast_0
0x180005d9d  mov     [rbx+30h], rax
0x180005da1  lea     rax, ?PageDlgProcRoot@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageProfileUseExisting@@$1?CLSID_WcnPageProfileUseExisting@@3U_GUID@@B$0A@$0DLH@$0MOL@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardPageUIBaseClass<1570,CWcnPageProfileUseExisting,&_GUID const CLSID_WcnPageProfileUseExisting,0,951,3307,0,0,0,0>::PageDlgProcRoot(HWND__ *,uint,unsigned __int64,__int64)
0x180005da8  mov     [rbx+28h], rax
0x180005dac  xor     eax, eax
0x180005dae  mov     qword ptr [rbx+10h], 3B7h
0x180005db6  mov     qword ptr [rbx+48h], 0CEBh
0x180005dbe  mov     qword ptr [rbx+50h], 0
0x180005dc6  mov     qword ptr [rbx+20h], 0
0x180005dce  mov     qword ptr [rbx+18h], 0
0x180005dd6  mov     [rsi], rbx
0x180005dd9  jmp     short loc_180005DE0
0x180005ddb  mov     eax, 8007000Eh
0x180005de0  mov     rbx, [rsp+58h+arg_0]
0x180005de5  mov     rsi, [rsp+58h+arg_8]
0x180005dea  add     rsp, 50h
0x180005dee  pop     rdi
0x180005def  retn
```

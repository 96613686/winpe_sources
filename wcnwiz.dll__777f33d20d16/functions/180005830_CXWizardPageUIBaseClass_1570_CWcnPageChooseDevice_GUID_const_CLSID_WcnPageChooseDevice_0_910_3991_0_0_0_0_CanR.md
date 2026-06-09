# CXWizardPageUIBaseClass<1570,CWcnPageChooseDevice,&_GUID const CLSID_WcnPageChooseDevice,0,910,3991,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005830`
- end: `0x180005950`
- name: `?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageChooseDevice@@$1?CLSID_WcnPageChooseDevice@@3U_GUID@@B$0A@$0DIO@$0PJH@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180004df0`

## callees

- `0x180002294`
- `0x180005740`
- `0x180005830`
- `0x18002f81c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800058a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800058a4`

## pseudocode

```c
__int64 __fastcall CXWizardPageUIBaseClass<1570,CWcnPageChooseDevice,&_GUID const CLSID_WcnPageChooseDevice,0,910,3991,0,0,0,0>::CanRunPage(
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
                                 &CXWizardPageUIBaseClass<1570,CWcnPageChooseDevice,&_GUID const CLSID_WcnPageChooseDevice,0,910,3991,0,0,0,0> `RTTI Type Descriptor',
                                 &CWcnPageChooseDevice `RTTI Type Descriptor',
                                 0);
        *((_QWORD *)v13 + 5) = CXWizardPageUIBaseClass<1570,CWcnPageChooseDevice,&_GUID const CLSID_WcnPageChooseDevice,0,910,3991,0,0,0,0>::PageDlgProcRoot;
        result = 0;
        *((_QWORD *)v13 + 2) = 910;
        *((_QWORD *)v13 + 9) = 3991;
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
0x180005830  mov     r11, rsp
0x180005833  mov     [r11+8], rbx
0x180005837  mov     [r11+10h], rsi
0x18000583b  push    rdi
0x18000583c  sub     rsp, 50h
0x180005840  mov     rax, [rsp+58h+arg_38]
0x180005848  mov     ebx, r9d
0x18000584b  mov     rsi, [rsp+58h+arg_40]
0x180005853  mov     rdi, rcx
0x180005856  mov     [r11-18h], rsi
0x18000585a  mov     [r11-20h], rax
0x18000585e  mov     eax, [rsp+58h+arg_30]
0x180005865  mov     [rsp+58h+var_28], eax; int
0x180005869  mov     rax, [rsp+58h+arg_28]
0x180005871  mov     [r11-30h], rax
0x180005875  mov     eax, [rsp+58h+arg_20]
0x18000587c  mov     [rsp+58h+var_38], eax; int
0x180005880  call    ?CanRunPage@?$CXWizardPageClass@VCWcnPageAuthNonUi@@$1?CLSID_WcnPageAuthNonUi@@3U_GUID@@B$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005885  test    eax, eax
0x180005887  js      loc_180005940
0x18000588d  test    ebx, 622h
0x180005893  jnz     short loc_18000589F
0x180005895  mov     eax, 80004001h
0x18000589a  jmp     loc_180005940
0x18000589f  mov     ecx, 68h ; 'h'; cb
0x1800058a4  call    cs:__imp_CoTaskMemAlloc
0x1800058aa  mov     rbx, rax
0x1800058ad  test    rax, rax
0x1800058b0  jz      loc_18000593B
0x1800058b6  xor     edx, edx; Val
0x1800058b8  lea     rcx, [rax+8]; void *
0x1800058bc  lea     r8d, [rdx+60h]; Size
0x1800058c0  call    memset_0
0x1800058c5  mov     dword ptr [rbx], 68h ; 'h'
0x1800058cb  lea     r9, ??_R0?AVCWcnPageChooseDevice@@@8; CWcnPageChooseDevice `RTTI Type Descriptor'
0x1800058d2  mov     dword ptr [rbx+4], 300Ch
0x1800058d9  lea     r8, ??_R0?AV?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageChooseDevice@@$1?CLSID_WcnPageChooseDevice@@3U_GUID@@B$0A@$0DIO@$0PJH@$0A@$0A@$0A@$0A@@@@8; CXWizardPageUIBaseClass<1570,CWcnPageChooseDevice,&_GUID const CLSID_WcnPageChooseDevice,0,910,3991,0,0,0,0> `RTTI Type Descriptor'
0x1800058e0  mov     rcx, cs:hModule
0x1800058e7  xor     edx, edx
0x1800058e9  mov     [rbx+8], rcx
0x1800058ed  mov     rcx, rdi
0x1800058f0  mov     [rsp+58h+var_38], 0
0x1800058f8  call    __RTDynamicCast_0
0x1800058fd  mov     [rbx+30h], rax
0x180005901  lea     rax, ?PageDlgProcRoot@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageChooseDevice@@$1?CLSID_WcnPageChooseDevice@@3U_GUID@@B$0A@$0DIO@$0PJH@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardPageUIBaseClass<1570,CWcnPageChooseDevice,&_GUID const CLSID_WcnPageChooseDevice,0,910,3991,0,0,0,0>::PageDlgProcRoot(HWND__ *,uint,unsigned __int64,__int64)
0x180005908  mov     [rbx+28h], rax
0x18000590c  xor     eax, eax
0x18000590e  mov     qword ptr [rbx+10h], 38Eh
0x180005916  mov     qword ptr [rbx+48h], 0F97h
0x18000591e  mov     qword ptr [rbx+50h], 0
0x180005926  mov     qword ptr [rbx+20h], 0
0x18000592e  mov     qword ptr [rbx+18h], 0
0x180005936  mov     [rsi], rbx
0x180005939  jmp     short loc_180005940
0x18000593b  mov     eax, 8007000Eh
0x180005940  mov     rbx, [rsp+58h+arg_0]
0x180005945  mov     rsi, [rsp+58h+arg_8]
0x18000594a  add     rsp, 50h
0x18000594e  pop     rdi
0x18000594f  retn
```

# CXWizardPageUIBaseClass<1570,CWcnPageProfileCreateNew,&_GUID const CLSID_WcnPageProfileCreateNew,0,950,3306,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005ba8`
- end: `0x180005cc8`
- name: `?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageProfileCreateNew@@$1?CLSID_WcnPageProfileCreateNew@@3U_GUID@@B$0A@$0DLG@$0MOK@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180005030`

## callees

- `0x180002294`
- `0x180005740`
- `0x180005ba8`
- `0x18002f81c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005c1c`

## pseudocode

```c
__int64 __fastcall CXWizardPageUIBaseClass<1570,CWcnPageProfileCreateNew,&_GUID const CLSID_WcnPageProfileCreateNew,0,950,3306,0,0,0,0>::CanRunPage(
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
                                 &CXWizardPageUIBaseClass<1570,CWcnPageProfileCreateNew,&_GUID const CLSID_WcnPageProfileCreateNew,0,950,3306,0,0,0,0> `RTTI Type Descriptor',
                                 &CWcnPageProfileCreateNew `RTTI Type Descriptor',
                                 0);
        *((_QWORD *)v13 + 5) = CXWizardPageUIBaseClass<1570,CWcnPageProfileCreateNew,&_GUID const CLSID_WcnPageProfileCreateNew,0,950,3306,0,0,0,0>::PageDlgProcRoot;
        result = 0;
        *((_QWORD *)v13 + 2) = 950;
        *((_QWORD *)v13 + 9) = 3306;
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
0x180005ba8  mov     r11, rsp
0x180005bab  mov     [r11+8], rbx
0x180005baf  mov     [r11+10h], rsi
0x180005bb3  push    rdi
0x180005bb4  sub     rsp, 50h
0x180005bb8  mov     rax, [rsp+58h+arg_38]
0x180005bc0  mov     ebx, r9d
0x180005bc3  mov     rsi, [rsp+58h+arg_40]
0x180005bcb  mov     rdi, rcx
0x180005bce  mov     [r11-18h], rsi
0x180005bd2  mov     [r11-20h], rax
0x180005bd6  mov     eax, [rsp+58h+arg_30]
0x180005bdd  mov     [rsp+58h+var_28], eax; int
0x180005be1  mov     rax, [rsp+58h+arg_28]
0x180005be9  mov     [r11-30h], rax
0x180005bed  mov     eax, [rsp+58h+arg_20]
0x180005bf4  mov     [rsp+58h+var_38], eax; int
0x180005bf8  call    ?CanRunPage@?$CXWizardPageClass@VCWcnPageAuthNonUi@@$1?CLSID_WcnPageAuthNonUi@@3U_GUID@@B$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005bfd  test    eax, eax
0x180005bff  js      loc_180005CB8
0x180005c05  test    ebx, 622h
0x180005c0b  jnz     short loc_180005C17
0x180005c0d  mov     eax, 80004001h
0x180005c12  jmp     loc_180005CB8
0x180005c17  mov     ecx, 68h ; 'h'; cb
0x180005c1c  call    cs:__imp_CoTaskMemAlloc
0x180005c22  mov     rbx, rax
0x180005c25  test    rax, rax
0x180005c28  jz      loc_180005CB3
0x180005c2e  xor     edx, edx; Val
0x180005c30  lea     rcx, [rax+8]; void *
0x180005c34  lea     r8d, [rdx+60h]; Size
0x180005c38  call    memset_0
0x180005c3d  mov     dword ptr [rbx], 68h ; 'h'
0x180005c43  lea     r9, ??_R0?AVCWcnPageProfileCreateNew@@@8; CWcnPageProfileCreateNew `RTTI Type Descriptor'
0x180005c4a  mov     dword ptr [rbx+4], 300Ch
0x180005c51  lea     r8, ??_R0?AV?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageProfileCreateNew@@$1?CLSID_WcnPageProfileCreateNew@@3U_GUID@@B$0A@$0DLG@$0MOK@$0A@$0A@$0A@$0A@@@@8; CXWizardPageUIBaseClass<1570,CWcnPageProfileCreateNew,&_GUID const CLSID_WcnPageProfileCreateNew,0,950,3306,0,0,0,0> `RTTI Type Descriptor'
0x180005c58  mov     rcx, cs:hModule
0x180005c5f  xor     edx, edx
0x180005c61  mov     [rbx+8], rcx
0x180005c65  mov     rcx, rdi
0x180005c68  mov     [rsp+58h+var_38], 0
0x180005c70  call    __RTDynamicCast_0
0x180005c75  mov     [rbx+30h], rax
0x180005c79  lea     rax, ?PageDlgProcRoot@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageProfileCreateNew@@$1?CLSID_WcnPageProfileCreateNew@@3U_GUID@@B$0A@$0DLG@$0MOK@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardPageUIBaseClass<1570,CWcnPageProfileCreateNew,&_GUID const CLSID_WcnPageProfileCreateNew,0,950,3306,0,0,0,0>::PageDlgProcRoot(HWND__ *,uint,unsigned __int64,__int64)
0x180005c80  mov     [rbx+28h], rax
0x180005c84  xor     eax, eax
0x180005c86  mov     qword ptr [rbx+10h], 3B6h
0x180005c8e  mov     qword ptr [rbx+48h], 0CEAh
0x180005c96  mov     qword ptr [rbx+50h], 0
0x180005c9e  mov     qword ptr [rbx+20h], 0
0x180005ca6  mov     qword ptr [rbx+18h], 0
0x180005cae  mov     [rsi], rbx
0x180005cb1  jmp     short loc_180005CB8
0x180005cb3  mov     eax, 8007000Eh
0x180005cb8  mov     rbx, [rsp+58h+arg_0]
0x180005cbd  mov     rsi, [rsp+58h+arg_8]
0x180005cc2  add     rsp, 50h
0x180005cc6  pop     rdi
0x180005cc7  retn
```

# CXWizardPageUIBaseClass<1570,CWcnPagePasswordPin,&_GUID const CLSID_WcnPagePasswordPin,0,501,3701,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005a80`
- end: `0x180005ba0`
- name: `?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPagePasswordPin@@$1?CLSID_WcnPagePasswordPin@@3U_GUID@@B$0A@$0BPF@$0OHF@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180004f70`

## callees

- `0x180002294`
- `0x180005740`
- `0x180005a80`
- `0x18002f81c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005af4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005af4`

## pseudocode

```c
__int64 __fastcall CXWizardPageUIBaseClass<1570,CWcnPagePasswordPin,&_GUID const CLSID_WcnPagePasswordPin,0,501,3701,0,0,0,0>::CanRunPage(
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
                                 &CXWizardPageUIBaseClass<1570,CWcnPagePasswordPin,&_GUID const CLSID_WcnPagePasswordPin,0,501,3701,0,0,0,0> `RTTI Type Descriptor',
                                 &CWcnPagePasswordPin `RTTI Type Descriptor',
                                 0);
        *((_QWORD *)v13 + 5) = CXWizardPageUIBaseClass<1570,CWcnPagePasswordPin,&_GUID const CLSID_WcnPagePasswordPin,0,501,3701,0,0,0,0>::PageDlgProcRoot;
        result = 0;
        *((_QWORD *)v13 + 2) = 501;
        *((_QWORD *)v13 + 9) = 3701;
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
0x180005a80  mov     r11, rsp
0x180005a83  mov     [r11+8], rbx
0x180005a87  mov     [r11+10h], rsi
0x180005a8b  push    rdi
0x180005a8c  sub     rsp, 50h
0x180005a90  mov     rax, [rsp+58h+arg_38]
0x180005a98  mov     ebx, r9d
0x180005a9b  mov     rsi, [rsp+58h+arg_40]
0x180005aa3  mov     rdi, rcx
0x180005aa6  mov     [r11-18h], rsi
0x180005aaa  mov     [r11-20h], rax
0x180005aae  mov     eax, [rsp+58h+arg_30]
0x180005ab5  mov     [rsp+58h+var_28], eax; int
0x180005ab9  mov     rax, [rsp+58h+arg_28]
0x180005ac1  mov     [r11-30h], rax
0x180005ac5  mov     eax, [rsp+58h+arg_20]
0x180005acc  mov     [rsp+58h+var_38], eax; int
0x180005ad0  call    ?CanRunPage@?$CXWizardPageClass@VCWcnPageAuthNonUi@@$1?CLSID_WcnPageAuthNonUi@@3U_GUID@@B$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x180005ad5  test    eax, eax
0x180005ad7  js      loc_180005B90
0x180005add  test    ebx, 622h
0x180005ae3  jnz     short loc_180005AEF
0x180005ae5  mov     eax, 80004001h
0x180005aea  jmp     loc_180005B90
0x180005aef  mov     ecx, 68h ; 'h'; cb
0x180005af4  call    cs:__imp_CoTaskMemAlloc
0x180005afa  mov     rbx, rax
0x180005afd  test    rax, rax
0x180005b00  jz      loc_180005B8B
0x180005b06  xor     edx, edx; Val
0x180005b08  lea     rcx, [rax+8]; void *
0x180005b0c  lea     r8d, [rdx+60h]; Size
0x180005b10  call    memset_0
0x180005b15  mov     dword ptr [rbx], 68h ; 'h'
0x180005b1b  lea     r9, ??_R0?AVCWcnPagePasswordPin@@@8; CWcnPagePasswordPin `RTTI Type Descriptor'
0x180005b22  mov     dword ptr [rbx+4], 300Ch
0x180005b29  lea     r8, ??_R0?AV?$CXWizardPageUIBaseClass@$0GCC@VCWcnPagePasswordPin@@$1?CLSID_WcnPagePasswordPin@@3U_GUID@@B$0A@$0BPF@$0OHF@$0A@$0A@$0A@$0A@@@@8; CXWizardPageUIBaseClass<1570,CWcnPagePasswordPin,&_GUID const CLSID_WcnPagePasswordPin,0,501,3701,0,0,0,0> `RTTI Type Descriptor'
0x180005b30  mov     rcx, cs:hModule
0x180005b37  xor     edx, edx
0x180005b39  mov     [rbx+8], rcx
0x180005b3d  mov     rcx, rdi
0x180005b40  mov     [rsp+58h+var_38], 0
0x180005b48  call    __RTDynamicCast_0
0x180005b4d  mov     [rbx+30h], rax
0x180005b51  lea     rax, ?PageDlgProcRoot@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPagePasswordPin@@$1?CLSID_WcnPagePasswordPin@@3U_GUID@@B$0A@$0BPF@$0OHF@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardPageUIBaseClass<1570,CWcnPagePasswordPin,&_GUID const CLSID_WcnPagePasswordPin,0,501,3701,0,0,0,0>::PageDlgProcRoot(HWND__ *,uint,unsigned __int64,__int64)
0x180005b58  mov     [rbx+28h], rax
0x180005b5c  xor     eax, eax
0x180005b5e  mov     qword ptr [rbx+10h], 1F5h
0x180005b66  mov     qword ptr [rbx+48h], 0E75h
0x180005b6e  mov     qword ptr [rbx+50h], 0
0x180005b76  mov     qword ptr [rbx+20h], 0
0x180005b7e  mov     qword ptr [rbx+18h], 0
0x180005b86  mov     [rsi], rbx
0x180005b89  jmp     short loc_180005B90
0x180005b8b  mov     eax, 8007000Eh
0x180005b90  mov     rbx, [rsp+58h+arg_0]
0x180005b95  mov     rsi, [rsp+58h+arg_8]
0x180005b9a  add     rsp, 50h
0x180005b9e  pop     rdi
0x180005b9f  retn
```

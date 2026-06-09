# CXWizardPageUIBaseClass<1570,CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,0,512,3339,0,0,0,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x180005958`
- end: `0x180005a78`
- name: `?CanRunPage@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageFinished@@$1?CLSID_WcnPageFinished@@3U_GUID@@B$0A@$0CAA@$0NAL@$0A@$0A@$0A@$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180004eb0`

## callees

- `0x180002294`
- `0x180005740`
- `0x180005958`
- `0x18002f81c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800059cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800059cc`

## pseudocode

```c
__int64 __fastcall CXWizardPageUIBaseClass<1570,CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,0,512,3339,0,0,0,0>::CanRunPage(
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
                                 &CXWizardPageUIBaseClass<1570,CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,0,512,3339,0,0,0,0> `RTTI Type Descriptor',
                                 &CWcnPageFinished `RTTI Type Descriptor',
                                 0);
        *((_QWORD *)v13 + 5) = CXWizardPageUIBaseClass<1570,CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,0,512,3339,0,0,0,0>::PageDlgProcRoot;
        result = 0;
        *((_QWORD *)v13 + 2) = 512;
        *((_QWORD *)v13 + 9) = 3339;
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
0x180005958  mov     r11, rsp
0x18000595b  mov     [r11+8], rbx
0x18000595f  mov     [r11+10h], rsi
0x180005963  push    rdi
0x180005964  sub     rsp, 50h
0x180005968  mov     rax, [rsp+58h+arg_38]
0x180005970  mov     ebx, r9d
0x180005973  mov     rsi, [rsp+58h+arg_40]
0x18000597b  mov     rdi, rcx
0x18000597e  mov     [r11-18h], rsi
0x180005982  mov     [r11-20h], rax
0x180005986  mov     eax, [rsp+58h+arg_30]
0x18000598d  mov     [rsp+58h+var_28], eax; int
0x180005991  mov     rax, [rsp+58h+arg_28]
0x180005999  mov     [r11-30h], rax
0x18000599d  mov     eax, [rsp+58h+arg_20]
0x1800059a4  mov     [rsp+58h+var_38], eax; int
0x1800059a8  call    ?CanRunPage@?$CXWizardPageClass@VCWcnPageAuthNonUi@@$1?CLSID_WcnPageAuthNonUi@@3U_GUID@@B$0A@@@UEAAJQEAU_GUID@@0W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z; CXWizardPageClass<CWcnPageAuthNonUi,&_GUID const CLSID_WcnPageAuthNonUi,0>::CanRunPage(_GUID * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)
0x1800059ad  test    eax, eax
0x1800059af  js      loc_180005A68
0x1800059b5  test    ebx, 622h
0x1800059bb  jnz     short loc_1800059C7
0x1800059bd  mov     eax, 80004001h
0x1800059c2  jmp     loc_180005A68
0x1800059c7  mov     ecx, 68h ; 'h'; cb
0x1800059cc  call    cs:__imp_CoTaskMemAlloc
0x1800059d2  mov     rbx, rax
0x1800059d5  test    rax, rax
0x1800059d8  jz      loc_180005A63
0x1800059de  xor     edx, edx; Val
0x1800059e0  lea     rcx, [rax+8]; void *
0x1800059e4  lea     r8d, [rdx+60h]; Size
0x1800059e8  call    memset_0
0x1800059ed  mov     dword ptr [rbx], 68h ; 'h'
0x1800059f3  lea     r9, ??_R0?AVCWcnPageFinished@@@8; CWcnPageFinished `RTTI Type Descriptor'
0x1800059fa  mov     dword ptr [rbx+4], 300Ch
0x180005a01  lea     r8, ??_R0?AV?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageFinished@@$1?CLSID_WcnPageFinished@@3U_GUID@@B$0A@$0CAA@$0NAL@$0A@$0A@$0A@$0A@@@@8; CXWizardPageUIBaseClass<1570,CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,0,512,3339,0,0,0,0> `RTTI Type Descriptor'
0x180005a08  mov     rcx, cs:hModule
0x180005a0f  xor     edx, edx
0x180005a11  mov     [rbx+8], rcx
0x180005a15  mov     rcx, rdi
0x180005a18  mov     [rsp+58h+var_38], 0
0x180005a20  call    __RTDynamicCast_0
0x180005a25  mov     [rbx+30h], rax
0x180005a29  lea     rax, ?PageDlgProcRoot@?$CXWizardPageUIBaseClass@$0GCC@VCWcnPageFinished@@$1?CLSID_WcnPageFinished@@3U_GUID@@B$0A@$0CAA@$0NAL@$0A@$0A@$0A@$0A@@@SA_JPEAUHWND__@@I_K_J@Z; CXWizardPageUIBaseClass<1570,CWcnPageFinished,&_GUID const CLSID_WcnPageFinished,0,512,3339,0,0,0,0>::PageDlgProcRoot(HWND__ *,uint,unsigned __int64,__int64)
0x180005a30  mov     [rbx+28h], rax
0x180005a34  xor     eax, eax
0x180005a36  mov     qword ptr [rbx+10h], 200h
0x180005a3e  mov     qword ptr [rbx+48h], 0D0Bh
0x180005a46  mov     qword ptr [rbx+50h], 0
0x180005a4e  mov     qword ptr [rbx+20h], 0
0x180005a56  mov     qword ptr [rbx+18h], 0
0x180005a5e  mov     [rsi], rbx
0x180005a61  jmp     short loc_180005A68
0x180005a63  mov     eax, 8007000Eh
0x180005a68  mov     rbx, [rsp+58h+arg_0]
0x180005a6d  mov     rsi, [rsp+58h+arg_8]
0x180005a72  add     rsp, 50h
0x180005a76  pop     rdi
0x180005a77  retn
```

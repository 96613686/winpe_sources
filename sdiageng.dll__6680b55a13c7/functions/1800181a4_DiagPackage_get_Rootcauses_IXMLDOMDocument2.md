# DiagPackage::get_Rootcauses(IXMLDOMDocument2 * *)

- ea: `0x1800181a4`
- end: `0x18001835e`
- name: `?get_Rootcauses@DiagPackage@@QEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180013b20`

## callees

- `0x1800181a4`
- `0x18001955c`
- `0x180026fa0`
- `0x180027ea4`
- `0x1800280f8`
- `0x18002a010`

## string_xrefs

- `0x1800181f9`: `<?xml version="1.0" encoding="utf-8"?><Rootcauses Version="1.0"/>`

## pseudocode

```c
__int64 __fastcall DiagPackage::get_Rootcauses(DiagPackage *this, struct IXMLDOMDocument2 **a2)
{
  int v4; // ebx
  struct IXMLDOMDocument2 *v5; // rdi
  int v6; // eax
  struct IXMLDOMDocument2 *v7; // r14
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rbp
  int v11; // eax
  struct IXMLDOMDocument2 *v12; // r15
  struct IXMLDOMDocument2 v13; // rax
  struct IXMLDOMDocument2 *v15; // [rsp+58h] [rbp+10h] BYREF

  v15 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    SdpDebugTrace(1u, L"DiagPackage::get_Rootcauses", 564, -2147024809);
    return (unsigned int)v4;
  }
  v5 = 0;
  v6 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Rootcauses Version=\"1.0\"/>", &v15);
  v7 = v15;
  v4 = v6;
  if ( v6 >= 0 )
  {
    v10 = 0;
    if ( !*((_DWORD *)this + 8) )
    {
LABEL_18:
      v13.lpVtbl = v7->lpVtbl;
      *a2 = v7;
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v13.lpVtbl->AddRef)(v7);
      goto LABEL_19;
    }
    while ( 1 )
    {
      if ( v5 )
      {
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->Release)(v5);
        v5 = 0;
      }
      v15 = 0;
      v11 = Rootcause::BuildResultXml((Rootcause *)(*((_QWORD *)this + 3) + 144 * v10), 0, &v15);
      v12 = v15;
      v4 = v11;
      if ( v11 >= 0 )
      {
        v5 = v15;
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v15->lpVtbl->AddRef)(v15);
      }
      else
      {
        SdpDebugTrace(1u, L"Rootcause::Describe", 594, v11);
      }
      if ( v12 )
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v12->lpVtbl->Release)(v12);
      if ( v4 < 0 )
        break;
      v6 = SdpXmlAppend(v7, 0, v5);
      v4 = v6;
      if ( v6 < 0 )
      {
        v8 = 576;
        goto LABEL_5;
      }
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= *((_DWORD *)this + 8) )
        goto LABEL_18;
    }
    v9 = v4;
    v8 = 573;
  }
  else
  {
    v8 = 567;
LABEL_5:
    v9 = v6;
  }
  SdpDebugTrace(1u, L"DiagPackage::get_Rootcauses", v8, v9);
LABEL_19:
  if ( v7 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v7->lpVtbl->Release)(v7);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v5->lpVtbl->Release)(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800181a4  mov     [rsp+arg_0], rbx
0x1800181a9  mov     [rsp+arg_10], rbp
0x1800181ae  push    rdi
0x1800181af  push    r12
0x1800181b1  push    r13
0x1800181b3  push    r14
0x1800181b5  push    r15
0x1800181b7  sub     rsp, 20h
0x1800181bb  mov     [rsp+48h+arg_8], 0
0x1800181c4  mov     r13, rdx
0x1800181c7  mov     r12, rcx
0x1800181ca  test    rdx, rdx
0x1800181cd  jnz     short loc_1800181F2
0x1800181cf  mov     ebx, 80070057h
0x1800181d4  lea     rdx, aDiagpackageGet_3; "DiagPackage::get_Rootcauses"
0x1800181db  mov     r9d, ebx; int
0x1800181de  lea     ecx, [r13+1]; Level
0x1800181e2  mov     r8d, 234h; int
0x1800181e8  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800181ed  jmp     loc_18001832B
0x1800181f2  lea     rdx, [rsp+48h+arg_8]; struct IXMLDOMDocument2 **
0x1800181f7  xor     edi, edi
0x1800181f9  lea     rcx, aXmlVersion10En_4; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180018200  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180018205  mov     r14, [rsp+48h+arg_8]
0x18001820a  mov     ebx, eax
0x18001820c  test    eax, eax
0x18001820e  jns     short loc_18001822F
0x180018210  mov     r8d, 237h; int
0x180018216  mov     r9d, eax; int
0x180018219  lea     rdx, aDiagpackageGet_3; "DiagPackage::get_Rootcauses"
0x180018220  mov     ecx, 1; Level
0x180018225  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001822a  jmp     loc_180018303
0x18001822f  xor     ebp, ebp
0x180018231  cmp     [r12+20h], edi
0x180018236  jbe     loc_1800182F0
0x18001823c  test    rdi, rdi
0x18001823f  jz      short loc_180018252
0x180018241  mov     rax, [rdi]
0x180018244  mov     rcx, rdi
0x180018247  mov     rax, [rax+10h]
0x18001824b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018250  xor     edi, edi
0x180018252  lea     rcx, ds:0[rbp*8]
0x18001825a  mov     [rsp+48h+arg_8], 0
0x180018263  add     rcx, rbp
0x180018266  lea     r8, [rsp+48h+arg_8]; struct IXMLDOMDocument2 **
0x18001826b  shl     rcx, 4
0x18001826f  xor     edx, edx; struct Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *
0x180018271  add     rcx, [r12+18h]; this
0x180018276  call    ?BuildResultXml@Rootcause@@AEAAJPEAU_SDIAG_ROOTCAUSE_INSTANCE@1@PEAPEAUIXMLDOMDocument2@@@Z; Rootcause::BuildResultXml(Rootcause::_SDIAG_ROOTCAUSE_INSTANCE *,IXMLDOMDocument2 * *)
0x18001827b  mov     r15, [rsp+48h+arg_8]
0x180018280  mov     ebx, eax
0x180018282  test    eax, eax
0x180018284  jns     short loc_1800182A2
0x180018286  mov     r9d, eax; int
0x180018289  lea     rdx, aRootcauseDescr; "Rootcause::Describe"
0x180018290  mov     r8d, 252h; int
0x180018296  mov     ecx, 1; Level
0x18001829b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800182a0  jmp     short loc_1800182B4
0x1800182a2  mov     rax, [r15]
0x1800182a5  mov     rcx, r15
0x1800182a8  mov     rdi, r15
0x1800182ab  mov     rax, [rax+8]
0x1800182af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182b4  test    r15, r15
0x1800182b7  jz      short loc_1800182C8
0x1800182b9  mov     rax, [r15]
0x1800182bc  mov     rcx, r15
0x1800182bf  mov     rax, [rax+10h]
0x1800182c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182c8  test    ebx, ebx
0x1800182ca  js      loc_180018350
0x1800182d0  mov     r8, rdi; struct IXMLDOMDocument2 *
0x1800182d3  xor     edx, edx; struct IXMLDOMElement *
0x1800182d5  mov     rcx, r14; struct IXMLDOMDocument2 *
0x1800182d8  call    ?SdpXmlAppend@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@0@Z; SdpXmlAppend(IXMLDOMDocument2 *,IXMLDOMElement *,IXMLDOMDocument2 *)
0x1800182dd  mov     ebx, eax
0x1800182df  test    eax, eax
0x1800182e1  js      short loc_180018345
0x1800182e3  inc     ebp
0x1800182e5  cmp     ebp, [r12+20h]
0x1800182ea  jb      loc_18001823C
0x1800182f0  mov     rax, [r14]
0x1800182f3  mov     rcx, r14
0x1800182f6  mov     [r13+0], r14
0x1800182fa  mov     rax, [rax+8]
0x1800182fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018303  test    r14, r14
0x180018306  jz      short loc_180018317
0x180018308  mov     rax, [r14]
0x18001830b  mov     rcx, r14
0x18001830e  mov     rax, [rax+10h]
0x180018312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018317  test    rdi, rdi
0x18001831a  jz      short loc_18001832B
0x18001831c  mov     rax, [rdi]
0x18001831f  mov     rcx, rdi
0x180018322  mov     rax, [rax+10h]
0x180018326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001832b  mov     rbp, [rsp+48h+arg_10]
0x180018330  mov     eax, ebx
0x180018332  mov     rbx, [rsp+48h+arg_0]
0x180018337  add     rsp, 20h
0x18001833b  pop     r15
0x18001833d  pop     r14
0x18001833f  pop     r13
0x180018341  pop     r12
0x180018343  pop     rdi
0x180018344  retn
0x180018345  mov     r8d, 240h
0x18001834b  jmp     loc_180018216
0x180018350  mov     r9d, ebx
0x180018353  mov     r8d, 23Dh
0x180018359  jmp     loc_180018219
```

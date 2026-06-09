# CPackage::SchdpInitializeNotification(IScriptedDiagnosticInformation *)

- ea: `0x180005260`
- end: `0x1800053fb`
- name: `?SchdpInitializeNotification@CPackage@@AEAAJPEAUIScriptedDiagnosticInformation@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct IScriptedDiagnosticInformation *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800046ac`

## callees

- `0x180001174`
- `0x180002de0`
- `0x180005260`
- `0x18000b13c`
- `0x18000b300`
- `0x18000b608`
- `0x18000d010`

## string_xrefs

- `0x1800052fe`: `./ExtensionPoint/Notification`

## pseudocode

```c
__int64 __fastcall CPackage::SchdpInitializeNotification(OLECHAR **this, struct IScriptedDiagnosticInformation *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  struct IXMLDOMDocument2 *v6; // rsi
  int Node; // eax
  struct IXMLDOMNode *v8; // rdi
  char *v9; // rax
  int v10; // r8d
  int v11; // eax
  struct IXMLDOMDocument2 *v13; // [rsp+40h] [rbp+8h] BYREF
  struct IXMLDOMNode *v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = 0;
  v14 = 0;
  v3 = (*(__int64 (__fastcall **)(struct IScriptedDiagnosticInformation *, char *))(*(_QWORD *)a2 + 88LL))(
         a2,
         (char *)this + 40);
  v4 = v3;
  if ( v3 < 0 )
  {
    SdpDebugTrace(1u, L"CPackage::SchdpInitializeNotification", 133, v3);
    return v4;
  }
  v5 = SdpXmlCreate(this[5], (LPVOID *)&v13);
  v6 = v13;
  v4 = v5;
  if ( v5 < 0 )
  {
    SdpDebugTrace(1u, L"CPackage::SchdpInitializeNotification", 136, v5);
    goto LABEL_17;
  }
  Node = SdpXmlGetNode(L"./ExtensionPoint/Notification", v13, 0, &v14);
  v4 = Node;
  if ( Node < 0 )
  {
    SdpDebugTrace(2u, L"CPackage::SchdpInitializeNotification", 142, Node);
    v4 = 0;
  }
  v8 = v14;
  if ( !v14 )
    goto LABEL_17;
  v9 = (char *)operator new(0x20u);
  if ( v9 )
  {
    *(_WORD *)v9 = 0;
    v9[2] = 0;
    *(_QWORD *)(v9 + 4) = 0;
    *((_DWORD *)v9 + 3) = 0;
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 3) = 0;
  }
  else
  {
    v9 = 0;
  }
  this[2] = (OLECHAR *)v9;
  if ( !v9 )
  {
    v4 = -2147024882;
    v10 = 146;
LABEL_15:
    SdpDebugTrace(1u, L"CPackage::SchdpInitializeNotification", v10, v4);
    goto LABEL_16;
  }
  v11 = CNotification::SchdpInitializeNotification((CNotification *)v9, v8);
  v4 = v11;
  if ( v11 < 0 )
  {
    SdpDebugTrace(1u, L"CNotification::Initialize", 891, v11);
    v10 = 153;
    goto LABEL_15;
  }
LABEL_16:
  ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
LABEL_17:
  if ( v6 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v6->lpVtbl->Release)(v6);
  return v4;
}

```

## disassembly

```asm
0x180005260  mov     rax, rsp
0x180005263  mov     [rax+18h], rbx
0x180005267  mov     [rax+20h], rbp
0x18000526b  push    rsi
0x18000526c  push    rdi
0x18000526d  push    r14
0x18000526f  sub     rsp, 20h
0x180005273  mov     r8, rdx
0x180005276  xor     r14d, r14d
0x180005279  mov     [rax+8], r14
0x18000527d  mov     rbp, rcx
0x180005280  mov     [rax+10h], r14
0x180005284  mov     rax, [rdx]
0x180005287  lea     rdx, [rcx+28h]
0x18000528b  mov     rcx, r8
0x18000528e  mov     rax, [rax+58h]
0x180005292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005297  mov     ebx, eax
0x180005299  test    eax, eax
0x18000529b  jns     short loc_1800052BB
0x18000529d  mov     r9d, eax; int
0x1800052a0  lea     rdx, aCpackageSchdpi; "CPackage::SchdpInitializeNotification"
0x1800052a7  mov     r8d, 85h; int
0x1800052ad  lea     ecx, [r14+1]; Level
0x1800052b1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800052b6  jmp     loc_1800053E5
0x1800052bb  mov     rcx, [rbp+28h]; psz
0x1800052bf  lea     rdx, [rsp+38h+arg_0]; struct IXMLDOMDocument2 **
0x1800052c4  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x1800052c9  mov     rsi, [rsp+38h+arg_0]
0x1800052ce  mov     ebx, eax
0x1800052d0  test    eax, eax
0x1800052d2  jns     short loc_1800052F3
0x1800052d4  mov     r9d, eax; int
0x1800052d7  lea     rdx, aCpackageSchdpi; "CPackage::SchdpInitializeNotification"
0x1800052de  mov     r8d, 88h; int
0x1800052e4  mov     ecx, 1; Level
0x1800052e9  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800052ee  jmp     loc_1800053D1
0x1800052f3  lea     r9, [rsp+38h+arg_8]; struct IXMLDOMNode **
0x1800052f8  xor     r8d, r8d; struct IXMLDOMNode *
0x1800052fb  mov     rdx, rsi; struct IXMLDOMDocument2 *
0x1800052fe  lea     rcx, aExtensionpoint; "./ExtensionPoint/Notification"
0x180005305  call    ?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z; SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)
0x18000530a  mov     ebx, eax
0x18000530c  test    eax, eax
0x18000530e  jns     short loc_18000532D
0x180005310  mov     r9d, eax; int
0x180005313  lea     rdx, aCpackageSchdpi; "CPackage::SchdpInitializeNotification"
0x18000531a  mov     r8d, 8Eh; int
0x180005320  mov     ecx, 2; Level
0x180005325  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000532a  mov     ebx, r14d
0x18000532d  mov     rdi, [rsp+38h+arg_8]
0x180005332  test    rdi, rdi
0x180005335  jz      loc_1800053D1
0x18000533b  mov     ecx, 20h ; ' '; Size
0x180005340  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005345  test    rax, rax
0x180005348  jz      short loc_180005364
0x18000534a  mov     [rax], r14w
0x18000534e  mov     [rax+2], r14b
0x180005352  mov     [rax+4], r14
0x180005356  mov     [rax+0Ch], r14d
0x18000535a  mov     [rax+10h], r14
0x18000535e  mov     [rax+18h], r14
0x180005362  jmp     short loc_180005367
0x180005364  mov     rax, r14
0x180005367  mov     [rbp+10h], rax
0x18000536b  test    rax, rax
0x18000536e  jnz     short loc_18000537D
0x180005370  mov     ebx, 8007000Eh
0x180005375  mov     r8d, 92h
0x18000537b  jmp     short loc_1800053AE
0x18000537d  mov     rdx, rdi; struct IXMLDOMNode *
0x180005380  mov     rcx, rax; this
0x180005383  call    ?SchdpInitializeNotification@CNotification@@AEAAJPEAUIXMLDOMNode@@@Z; CNotification::SchdpInitializeNotification(IXMLDOMNode *)
0x180005388  mov     ebx, eax
0x18000538a  test    eax, eax
0x18000538c  jns     short loc_1800053C2
0x18000538e  mov     r9d, eax; int
0x180005391  lea     rdx, aCnotificationI; "CNotification::Initialize"
0x180005398  mov     r8d, 37Bh; int
0x18000539e  mov     ecx, 1; Level
0x1800053a3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800053a8  mov     r8d, 99h; int
0x1800053ae  mov     r9d, ebx; int
0x1800053b1  lea     rdx, aCpackageSchdpi; "CPackage::SchdpInitializeNotification"
0x1800053b8  mov     ecx, 1; Level
0x1800053bd  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800053c2  mov     rax, [rdi]
0x1800053c5  mov     rcx, rdi
0x1800053c8  mov     rax, [rax+10h]
0x1800053cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053d1  test    rsi, rsi
0x1800053d4  jz      short loc_1800053E5
0x1800053d6  mov     rax, [rsi]
0x1800053d9  mov     rcx, rsi
0x1800053dc  mov     rax, [rax+10h]
0x1800053e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e5  mov     rbp, [rsp+38h+arg_18]
0x1800053ea  mov     eax, ebx
0x1800053ec  mov     rbx, [rsp+38h+arg_10]
0x1800053f1  add     rsp, 20h
0x1800053f5  pop     r14
0x1800053f7  pop     rdi
0x1800053f8  pop     rsi
0x1800053f9  retn
```

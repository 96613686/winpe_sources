# Reporter::AddIsAdminToReport(IXMLDOMElement *,IXMLDOMDocument2 *)

- ea: `0x180020fc0`
- end: `0x180021143`
- name: `?AddIsAdminToReport@Reporter@@AEAAJPEAUIXMLDOMElement@@PEAUIXMLDOMDocument2@@@Z`
- size: `387`
- prototype: `__int64 __fastcall(Reporter *this, struct IXMLDOMElement *, struct IXMLDOMDocument2 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180021ec4`
- `0x180022174`

## callees

- `0x1800012a4`
- `0x180005ffc`
- `0x180020fc0`
- `0x180026fa0`
- `0x18002744c`
- `0x18002827c`
- `0x1800291e0`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Reporter::AddIsAdminToReport(Reporter *this, struct IXMLDOMElement *a2, struct IXMLDOMDocument2 *a3)
{
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // ebx
  int IsAdmin; // eax
  const unsigned __int16 *v9; // r9
  int v10; // eax
  struct IXMLDOMElement *v11; // rdi
  int v12; // r8d
  int String; // eax
  void *v14; // rsi
  int v15; // r8d
  int v17; // [rsp+50h] [rbp+8h] BYREF
  int v18; // [rsp+54h] [rbp+Ch]
  struct IXMLDOMElement *v19; // [rsp+58h] [rbp+10h] BYREF
  void *Block; // [rsp+68h] [rbp+20h] BYREF

  v18 = HIDWORD(this);
  Block = 0;
  v19 = 0;
  v17 = 0;
  if ( !a2 )
  {
    v5 = 766;
LABEL_3:
    v6 = -2147024809;
    v7 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"Reporter::AddIsAdminToReport", v5, v6);
    return v7;
  }
  if ( !a3 )
  {
    v5 = 767;
    goto LABEL_3;
  }
  IsAdmin = SdpIsAdmin(&v17);
  v7 = IsAdmin;
  if ( IsAdmin < 0 )
  {
    v6 = IsAdmin;
    v5 = 774;
    goto LABEL_4;
  }
  v9 = L"true";
  if ( !v17 )
    v9 = L"false";
  v10 = SdpXmlCreateNode(a3, a2, L"Data", v9, &v19);
  v11 = v19;
  v7 = v10;
  if ( v10 >= 0 )
  {
    v10 = SdpXmlSetAttribute(0, v19, L"id", L"RunningAsAdmin");
    v7 = v10;
    if ( v10 < 0 )
    {
      v12 = 798;
      goto LABEL_13;
    }
    String = SdpLoadString(0, 0x7Fu, (unsigned __int16 **)&Block);
    v14 = Block;
    v7 = String;
    if ( String >= 0 )
    {
      String = SdpXmlSetAttribute(0, v11, L"name", (const unsigned __int16 *)Block);
      v7 = String;
      if ( String >= 0 )
        goto LABEL_21;
      v15 = 804;
    }
    else
    {
      v15 = 801;
    }
    SdpDebugTrace(1u, L"Reporter::AddIsAdminToReport", v15, String);
LABEL_21:
    if ( v14 )
      operator delete(v14);
    goto LABEL_23;
  }
  v12 = 792;
LABEL_13:
  SdpDebugTrace(1u, L"Reporter::AddIsAdminToReport", v12, v10);
LABEL_23:
  if ( v11 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v11->lpVtbl->Release)(v11);
  return v7;
}

```

## disassembly

```asm
0x180020fc0  mov     rax, rsp
0x180020fc3  mov     [rax+8], rcx
0x180020fc7  push    rbx
0x180020fc8  push    rsi
0x180020fc9  push    rdi
0x180020fca  sub     rsp, 30h
0x180020fce  mov     qword ptr [rax+20h], 0
0x180020fd6  mov     rdi, r8
0x180020fd9  mov     qword ptr [rax+10h], 0
0x180020fe1  mov     rsi, rdx
0x180020fe4  mov     dword ptr [rax+8], 0
0x180020feb  test    rdx, rdx
0x180020fee  jnz     short loc_180021015
0x180020ff0  mov     r8d, 2FEh; int
0x180020ff6  mov     r9d, 80070057h; int
0x180020ffc  mov     ebx, r9d
0x180020fff  lea     rdx, aReporterAddisa; "Reporter::AddIsAdminToReport"
0x180021006  mov     ecx, 1; Level
0x18002100b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021010  jmp     loc_180021139
0x180021015  test    rdi, rdi
0x180021018  jnz     short loc_180021022
0x18002101a  mov     r8d, 2FFh
0x180021020  jmp     short loc_180020FF6
0x180021022  lea     rcx, [rsp+48h+arg_0]; int *
0x180021027  call    ?SdpIsAdmin@@YAJPEAH@Z; SdpIsAdmin(int *)
0x18002102c  mov     ebx, eax
0x18002102e  test    eax, eax
0x180021030  jns     short loc_18002103D
0x180021032  mov     r9d, eax
0x180021035  mov     r8d, 306h
0x18002103b  jmp     short loc_180020FFF
0x18002103d  cmp     [rsp+48h+arg_0], 0
0x180021042  lea     rax, aFalse; "false"
0x180021049  lea     r9, aTrue; "true"
0x180021050  mov     rdx, rsi; struct IXMLDOMElement *
0x180021053  cmovz   r9, rax; unsigned __int16 *
0x180021057  lea     r8, aData; "Data"
0x18002105e  lea     rax, [rsp+48h+arg_8]
0x180021063  mov     rcx, rdi; struct IXMLDOMDocument2 *
0x180021066  mov     [rsp+48h+var_28], rax; struct IXMLDOMElement **
0x18002106b  call    ?SdpXmlCreateNode@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2PEAPEAU2@@Z; SdpXmlCreateNode(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *,IXMLDOMElement * *)
0x180021070  mov     rdi, [rsp+48h+arg_8]
0x180021075  mov     ebx, eax
0x180021077  test    eax, eax
0x180021079  jns     short loc_18002109A
0x18002107b  mov     r8d, 318h; int
0x180021081  mov     r9d, eax; int
0x180021084  lea     rdx, aReporterAddisa; "Reporter::AddIsAdminToReport"
0x18002108b  mov     ecx, 1; Level
0x180021090  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021095  jmp     loc_180021125
0x18002109a  lea     r9, aRunningasadmin; "RunningAsAdmin"
0x1800210a1  mov     rdx, rdi; struct IXMLDOMElement *
0x1800210a4  lea     r8, aId_0; "id"
0x1800210ab  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x1800210ad  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800210b2  mov     ebx, eax
0x1800210b4  test    eax, eax
0x1800210b6  jns     short loc_1800210C0
0x1800210b8  mov     r8d, 31Eh
0x1800210be  jmp     short loc_180021081
0x1800210c0  lea     r8, [rsp+48h+Block]; unsigned __int16 **
0x1800210c5  mov     edx, 7Fh; unsigned int
0x1800210ca  xor     ecx, ecx; unsigned __int16 *
0x1800210cc  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x1800210d1  mov     rsi, [rsp+48h+Block]
0x1800210d6  mov     ebx, eax
0x1800210d8  test    eax, eax
0x1800210da  jns     short loc_1800210E4
0x1800210dc  mov     r8d, 321h
0x1800210e2  jmp     short loc_180021104
0x1800210e4  mov     r9, rsi; unsigned __int16 *
0x1800210e7  lea     r8, aName_0; "name"
0x1800210ee  mov     rdx, rdi; struct IXMLDOMElement *
0x1800210f1  xor     ecx, ecx; struct IXMLDOMDocument2 *
0x1800210f3  call    ?SdpXmlSetAttribute@@YAJPEAUIXMLDOMDocument2@@PEAUIXMLDOMElement@@PEBG2@Z; SdpXmlSetAttribute(IXMLDOMDocument2 *,IXMLDOMElement *,ushort const *,ushort const *)
0x1800210f8  mov     ebx, eax
0x1800210fa  test    eax, eax
0x1800210fc  jns     short loc_180021118
0x1800210fe  mov     r8d, 324h; int
0x180021104  mov     r9d, eax; int
0x180021107  lea     rdx, aReporterAddisa; "Reporter::AddIsAdminToReport"
0x18002110e  mov     ecx, 1; Level
0x180021113  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180021118  test    rsi, rsi
0x18002111b  jz      short loc_180021125
0x18002111d  mov     rcx, rsi; Block
0x180021120  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021125  test    rdi, rdi
0x180021128  jz      short loc_180021139
0x18002112a  mov     rax, [rdi]
0x18002112d  mov     rcx, rdi
0x180021130  mov     rax, [rax+10h]
0x180021134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021139  mov     eax, ebx
0x18002113b  add     rsp, 30h
0x18002113f  pop     rdi
0x180021140  pop     rsi
0x180021141  pop     rbx
0x180021142  retn
```

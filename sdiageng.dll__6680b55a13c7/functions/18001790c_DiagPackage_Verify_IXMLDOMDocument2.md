# DiagPackage::Verify(IXMLDOMDocument2 * *)

- ea: `0x18001790c`
- end: `0x180017a2b`
- name: `?Verify@DiagPackage@@QEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180011630`

## callees

- `0x18001790c`
- `0x18001b2d0`
- `0x180026fa0`
- `0x1800280f8`
- `0x18002a010`

## string_xrefs

- `0x180017959`: `<?xml version="1.0" encoding="utf-8"?><Rootcauses Version="1.0"/>`

## pseudocode

```c
__int64 __fastcall DiagPackage::Verify(DiagPackage *this, struct IXMLDOMDocument2 **a2)
{
  struct IXMLDOMDocument2 *v2; // rbx
  unsigned int v5; // edi
  int v6; // r8d
  int v7; // r9d
  int v8; // eax
  int v9; // r9d
  int v10; // r8d
  __int64 v11; // rbp
  Rootcause *v12; // rcx
  int v13; // eax
  struct IXMLDOMDocument2 v14; // rax
  struct IXMLDOMDocument2 *v16; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  v16 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 329;
    v7 = -2147024809;
LABEL_3:
    SdpDebugTrace(1u, L"DiagPackage::Verify", v6, v7);
    goto LABEL_13;
  }
  v8 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Rootcauses Version=\"1.0\"/>", &v16);
  v5 = v8;
  if ( v8 < 0 )
  {
    v9 = v8;
    v10 = 332;
LABEL_6:
    SdpDebugTrace(1u, L"DiagPackage::Verify", v10, v9);
    v2 = v16;
    goto LABEL_13;
  }
  if ( !*((_QWORD *)this + 3) )
  {
    v5 = -2147467261;
    v10 = 334;
    v9 = -2147467261;
    goto LABEL_6;
  }
  v2 = v16;
  v11 = 0;
  if ( *((_DWORD *)this + 8) )
  {
    while ( 1 )
    {
      v12 = (Rootcause *)(*((_QWORD *)this + 3) + 144 * v11);
      *((_QWORD *)this + 12) = v12;
      v13 = Rootcause::Verify(v12, v2);
      v5 = v13;
      if ( v13 < 0 )
        break;
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= *((_DWORD *)this + 8) )
        goto LABEL_12;
    }
    v7 = v13;
    v6 = 344;
    goto LABEL_3;
  }
LABEL_12:
  v14.lpVtbl = v2->lpVtbl;
  *a2 = v2;
  ((void (__fastcall *)(struct IXMLDOMDocument2 *))v14.lpVtbl->AddRef)(v2);
LABEL_13:
  *((_QWORD *)this + 12) = 0;
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v2->lpVtbl->Release)(v2);
  return v5;
}

```

## disassembly

```asm
0x18001790c  mov     [rsp+arg_8], rbx
0x180017911  mov     [rsp+arg_10], rbp
0x180017916  push    rsi
0x180017917  push    rdi
0x180017918  push    r14
0x18001791a  sub     rsp, 20h
0x18001791e  xor     ebx, ebx
0x180017920  mov     r14, rdx
0x180017923  mov     [rsp+38h+arg_0], rbx
0x180017928  mov     rsi, rcx
0x18001792b  test    rdx, rdx
0x18001792e  jnz     short loc_180017954
0x180017930  mov     edi, 80070057h
0x180017935  mov     r8d, 149h; int
0x18001793b  mov     r9d, edi; int
0x18001793e  lea     rdx, aDiagpackageVer; "DiagPackage::Verify"
0x180017945  mov     ecx, 1; Level
0x18001794a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001794f  jmp     loc_1800179EC
0x180017954  lea     rdx, [rsp+38h+arg_0]; struct IXMLDOMDocument2 **
0x180017959  lea     rcx, aXmlVersion10En_4; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180017960  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180017965  mov     edi, eax
0x180017967  test    eax, eax
0x180017969  jns     short loc_18001798C
0x18001796b  mov     r9d, eax; int
0x18001796e  mov     r8d, 14Ch; int
0x180017974  lea     rdx, aDiagpackageVer; "DiagPackage::Verify"
0x18001797b  mov     ecx, 1; Level
0x180017980  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180017985  mov     rbx, [rsp+38h+arg_0]
0x18001798a  jmp     short loc_1800179EC
0x18001798c  cmp     [rsi+18h], rbx
0x180017990  jnz     short loc_1800179A2
0x180017992  mov     edi, 80004003h
0x180017997  mov     r8d, 14Eh
0x18001799d  mov     r9d, edi
0x1800179a0  jmp     short loc_180017974
0x1800179a2  mov     rbx, [rsp+38h+arg_0]
0x1800179a7  xor     ebp, ebp
0x1800179a9  cmp     [rsi+20h], ebp
0x1800179ac  jbe     short loc_1800179DA
0x1800179ae  lea     rcx, ds:0[rbp*8]
0x1800179b6  mov     rdx, rbx; struct IXMLDOMDocument2 *
0x1800179b9  add     rcx, rbp
0x1800179bc  shl     rcx, 4
0x1800179c0  add     rcx, [rsi+18h]; this
0x1800179c4  mov     [rsi+60h], rcx
0x1800179c8  call    ?Verify@Rootcause@@QEAAJPEAUIXMLDOMDocument2@@@Z; Rootcause::Verify(IXMLDOMDocument2 *)
0x1800179cd  mov     edi, eax
0x1800179cf  test    eax, eax
0x1800179d1  js      short loc_180017A1D
0x1800179d3  inc     ebp
0x1800179d5  cmp     ebp, [rsi+20h]
0x1800179d8  jb      short loc_1800179AE
0x1800179da  mov     rax, [rbx]
0x1800179dd  mov     rcx, rbx
0x1800179e0  mov     [r14], rbx
0x1800179e3  mov     rax, [rax+8]
0x1800179e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179ec  mov     qword ptr [rsi+60h], 0
0x1800179f4  test    rbx, rbx
0x1800179f7  jz      short loc_180017A08
0x1800179f9  mov     rax, [rbx]
0x1800179fc  mov     rcx, rbx
0x1800179ff  mov     rax, [rax+10h]
0x180017a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a08  mov     rbx, [rsp+38h+arg_8]
0x180017a0d  mov     eax, edi
0x180017a0f  mov     rbp, [rsp+38h+arg_10]
0x180017a14  add     rsp, 20h
0x180017a18  pop     r14
0x180017a1a  pop     rdi
0x180017a1b  pop     rsi
0x180017a1c  retn
0x180017a1d  mov     r9d, eax
0x180017a20  mov     r8d, 158h
0x180017a26  jmp     loc_18001793E
```

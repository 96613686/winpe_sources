# DiagPackage::InitializeTroubleshooter(IXMLDOMNode *)

- ea: `0x180016460`
- end: `0x180016512`
- name: `?InitializeTroubleshooter@DiagPackage@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(DiagPackage *this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016630`

## callees

- `0x180001264`
- `0x180016460`
- `0x18001bdac`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall DiagPackage::InitializeTroubleshooter(DiagPackage *this, struct IXMLDOMNode *a2)
{
  unsigned int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  Troubleshooter *v7; // rax
  struct Settings *v8; // rdx
  int v9; // eax

  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 1362;
    v6 = -2147024809;
LABEL_11:
    SdpDebugTrace(1u, L"DiagPackage::InitializeTroubleshooter", v5, v6);
    return v4;
  }
  v7 = (Troubleshooter *)operator new(0x10u);
  if ( v7 )
  {
    *(_QWORD *)v7 = 0;
    *((_QWORD *)v7 + 1) = 0;
  }
  *((_QWORD *)this + 2) = v7;
  if ( !v7 )
  {
    v4 = -2147024882;
    v5 = 1365;
    v6 = -2147024882;
    goto LABEL_11;
  }
  v8 = (struct Settings *)*((_QWORD *)this + 1);
  if ( !v8 )
  {
    v4 = -2147467261;
    v5 = 1367;
    v6 = -2147467261;
    goto LABEL_11;
  }
  v9 = Troubleshooter::Initialize(v7, v8, a2);
  v4 = v9;
  if ( v9 < 0 )
  {
    v6 = v9;
    v5 = 1370;
    goto LABEL_11;
  }
  return v4;
}

```

## disassembly

```asm
0x180016460  mov     [rsp+arg_0], rbx
0x180016465  push    rdi
0x180016466  sub     rsp, 20h
0x18001646a  mov     rdi, rdx
0x18001646d  mov     rbx, rcx
0x180016470  test    rdx, rdx
0x180016473  jnz     short loc_180016485
0x180016475  mov     ebx, 80070057h
0x18001647a  mov     r8d, 552h
0x180016480  mov     r9d, ebx
0x180016483  jmp     short loc_1800164F4
0x180016485  mov     ecx, 10h; Size
0x18001648a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001648f  mov     [rsp+28h+arg_8], rax
0x180016494  test    rax, rax
0x180016497  jz      short loc_1800164A8
0x180016499  mov     qword ptr [rax], 0
0x1800164a0  mov     qword ptr [rax+8], 0
0x1800164a8  mov     [rbx+10h], rax
0x1800164ac  test    rax, rax
0x1800164af  jnz     short loc_1800164C1
0x1800164b1  mov     ebx, 8007000Eh
0x1800164b6  mov     r8d, 555h
0x1800164bc  mov     r9d, ebx
0x1800164bf  jmp     short loc_1800164F4
0x1800164c1  mov     rdx, [rbx+8]; struct Settings *
0x1800164c5  test    rdx, rdx
0x1800164c8  jnz     short loc_1800164DA
0x1800164ca  mov     ebx, 80004003h
0x1800164cf  mov     r8d, 557h
0x1800164d5  mov     r9d, ebx
0x1800164d8  jmp     short loc_1800164F4
0x1800164da  mov     r8, rdi; struct IXMLDOMNode *
0x1800164dd  mov     rcx, rax; this
0x1800164e0  call    ?Initialize@Troubleshooter@@QEAAJPEAVSettings@@PEAUIXMLDOMNode@@@Z; Troubleshooter::Initialize(Settings *,IXMLDOMNode *)
0x1800164e5  mov     ebx, eax
0x1800164e7  test    eax, eax
0x1800164e9  jns     short loc_180016505
0x1800164eb  mov     r9d, eax; int
0x1800164ee  mov     r8d, 55Ah; int
0x1800164f4  lea     rdx, aDiagpackageIni_2; "DiagPackage::InitializeTroubleshooter"
0x1800164fb  mov     ecx, 1; Level
0x180016500  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180016505  mov     eax, ebx
0x180016507  mov     rbx, [rsp+28h+arg_0]
0x18001650c  add     rsp, 20h
0x180016510  pop     rdi
0x180016511  retn
```

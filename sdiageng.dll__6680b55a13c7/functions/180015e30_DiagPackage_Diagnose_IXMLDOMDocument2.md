# DiagPackage::Diagnose(IXMLDOMDocument2 * *)

- ea: `0x180015e30`
- end: `0x180016077`
- name: `?Diagnose@DiagPackage@@QEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000ad80`

## callees

- `0x180015e30`
- `0x18001ad00`
- `0x18001b4d4`
- `0x18001c110`
- `0x180026fa0`
- `0x1800280f8`
- `0x18002a010`

## string_xrefs

- `0x180015fd4`: `<?xml version="1.0" encoding="utf-8"?><DetailedInformation/>`
- `0x180015e8c`: `<?xml version="1.0" encoding="utf-8"?><Rootcauses Version="1.0"/>`

## pseudocode

```c
__int64 __fastcall DiagPackage::Diagnose(DiagPackage *this, struct IXMLDOMDocument2 **a2)
{
  struct IXMLDOMDocument2 *v2; // r14
  int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  int v8; // eax
  int v9; // r9d
  int v10; // r8d
  unsigned int v11; // eax
  __int64 i; // rbp
  Troubleshooter *v13; // rcx
  int v14; // eax
  __int64 v15; // rbp
  __int64 v16; // rcx
  Troubleshooter *v17; // rcx
  int v18; // eax
  __int64 v19; // rbp
  int DiagnosisResult; // eax
  struct IXMLDOMDocument2 v21; // rax
  __int64 v22; // rcx
  __int64 j; // rbp
  int v25; // r8d
  int v26; // r9d
  struct IXMLDOMDocument2 *v27; // [rsp+60h] [rbp+8h] BYREF

  v2 = 0;
  v27 = 0;
  if ( a2 )
  {
    if ( (*(_BYTE *)this & 1) == 0 )
    {
      v5 = -2143551224;
      v6 = 165;
      goto LABEL_3;
    }
    v8 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><Rootcauses Version=\"1.0\"/>", &v27);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = v8;
      v10 = 169;
LABEL_16:
      SdpDebugTrace(1u, L"DiagPackage::Diagnose", v10, v9);
      v2 = v27;
      goto LABEL_25;
    }
    v11 = *((_DWORD *)this + 8);
    for ( i = 0; (unsigned int)i < v11; i = (unsigned int)(i + 1) )
    {
      Rootcause::Reset((Rootcause *)(*((_QWORD *)this + 3) + 144 * i), 0);
      v11 = *((_DWORD *)this + 8);
    }
    v13 = (Troubleshooter *)*((_QWORD *)this + 2);
    if ( v13 )
    {
      v14 = Troubleshooter::Run(v13);
      v5 = v14;
      if ( v14 < 0 )
      {
        v9 = v14;
        v10 = 186;
        goto LABEL_16;
      }
    }
    else
    {
      if ( !*((_QWORD *)this + 3) )
      {
        v9 = -2147467261;
        v10 = 189;
        v5 = -2147467261;
        goto LABEL_16;
      }
      v15 = 0;
      if ( v11 )
      {
        while ( 1 )
        {
          v16 = *((_QWORD *)this + 3) + 144 * v15;
          *((_QWORD *)this + 12) = v16;
          v17 = *(Troubleshooter **)(v16 + 8);
          if ( !v17 )
            break;
          v18 = Troubleshooter::Run(v17);
          v5 = v18;
          if ( v18 < 0 )
          {
            v25 = 183;
            v26 = v18;
            goto LABEL_34;
          }
          v15 = (unsigned int)(v15 + 1);
          if ( (unsigned int)v15 >= *((_DWORD *)this + 8) )
            goto LABEL_21;
        }
        v26 = -2147467261;
        v25 = 176;
        v5 = -2147467261;
LABEL_34:
        SdpDebugTrace(1u, L"Rootcause::Diagnose", v25, v26);
        v9 = v5;
        v10 = 194;
        goto LABEL_16;
      }
    }
LABEL_21:
    v2 = v27;
    v19 = 0;
    if ( !*((_DWORD *)this + 8) )
    {
LABEL_24:
      v21.lpVtbl = v2->lpVtbl;
      *a2 = v2;
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v21.lpVtbl->AddRef)(v2);
      if ( v5 >= 0 )
        goto LABEL_29;
      goto LABEL_25;
    }
    while ( 1 )
    {
      DiagnosisResult = Rootcause::get_DiagnosisResult((Rootcause *)(*((_QWORD *)this + 3) + 144 * v19), v2);
      v5 = DiagnosisResult;
      if ( DiagnosisResult < 0 )
        break;
      v19 = (unsigned int)(v19 + 1);
      if ( (unsigned int)v19 >= *((_DWORD *)this + 8) )
        goto LABEL_24;
    }
    v7 = DiagnosisResult;
    v6 = 204;
    goto LABEL_4;
  }
  v5 = -2147024809;
  v6 = 157;
LABEL_3:
  v7 = v5;
LABEL_4:
  SdpDebugTrace(1u, L"DiagPackage::Diagnose", v6, v7);
LABEL_25:
  v22 = *((_QWORD *)this + 16);
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    *((_QWORD *)this + 16) = 0;
  }
  SdpXmlCreate(
    (OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><DetailedInformation/>",
    (struct IXMLDOMDocument2 **)this + 16);
  for ( j = 0; (unsigned int)j < *((_DWORD *)this + 8); j = (unsigned int)(j + 1) )
    Rootcause::Reset((Rootcause *)(*((_QWORD *)this + 3) + 144 * j), 1);
LABEL_29:
  *((_QWORD *)this + 12) = 0;
  if ( v2 )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))v2->lpVtbl->Release)(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180015e30  push    rbx
0x180015e32  push    rbp
0x180015e33  push    rsi
0x180015e34  push    rdi
0x180015e35  push    r14
0x180015e37  push    r15
0x180015e39  sub     rsp, 28h
0x180015e3d  xor     r14d, r14d
0x180015e40  mov     r15, rdx
0x180015e43  mov     [rsp+58h+arg_0], r14
0x180015e48  mov     rdi, rcx
0x180015e4b  lea     esi, [r14+1]
0x180015e4f  test    rdx, rdx
0x180015e52  jnz     short loc_180015E75
0x180015e54  mov     ebx, 80070057h
0x180015e59  mov     r8d, 9Dh; int
0x180015e5f  mov     r9d, ebx; int
0x180015e62  lea     rdx, aDiagpackageDia; "DiagPackage::Diagnose"
0x180015e69  mov     ecx, esi; Level
0x180015e6b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015e70  jmp     loc_180015FAF
0x180015e75  test    [rcx], sil
0x180015e78  jnz     short loc_180015E87
0x180015e7a  mov     ebx, 803C0108h
0x180015e7f  mov     r8d, 0A5h
0x180015e85  jmp     short loc_180015E5F
0x180015e87  lea     rdx, [rsp+58h+arg_0]; struct IXMLDOMDocument2 **
0x180015e8c  lea     rcx, aXmlVersion10En_4; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180015e93  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180015e98  mov     ebx, eax
0x180015e9a  test    eax, eax
0x180015e9c  jns     short loc_180015EA9
0x180015e9e  mov     r9d, eax
0x180015ea1  mov     r8d, 0A9h
0x180015ea7  jmp     short loc_180015F09
0x180015ea9  mov     eax, [rdi+20h]
0x180015eac  xor     ebp, ebp
0x180015eae  test    eax, eax
0x180015eb0  jz      short loc_180015ED5
0x180015eb2  lea     rcx, ds:0[rbp*8]
0x180015eba  xor     edx, edx; int
0x180015ebc  add     rcx, rbp
0x180015ebf  shl     rcx, 4
0x180015ec3  add     rcx, [rdi+18h]; this
0x180015ec7  call    ?Reset@Rootcause@@QEAAJH@Z; Rootcause::Reset(int)
0x180015ecc  mov     eax, [rdi+20h]
0x180015ecf  add     ebp, esi
0x180015ed1  cmp     ebp, eax
0x180015ed3  jb      short loc_180015EB2
0x180015ed5  mov     rcx, [rdi+10h]; this
0x180015ed9  test    rcx, rcx
0x180015edc  jz      short loc_180015EF4
0x180015ede  call    ?Run@Troubleshooter@@QEAAJXZ; Troubleshooter::Run(void)
0x180015ee3  mov     ebx, eax
0x180015ee5  test    eax, eax
0x180015ee7  jns     short loc_180015F61
0x180015ee9  mov     r9d, eax
0x180015eec  mov     r8d, 0BAh
0x180015ef2  jmp     short loc_180015F09
0x180015ef4  cmp     [rdi+18h], r14
0x180015ef8  jnz     short loc_180015F21
0x180015efa  mov     r9d, 80004003h; int
0x180015f00  mov     r8d, 0BDh; int
0x180015f06  mov     ebx, r9d
0x180015f09  lea     rdx, aDiagpackageDia; "DiagPackage::Diagnose"
0x180015f10  mov     ecx, esi; Level
0x180015f12  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180015f17  mov     r14, [rsp+58h+arg_0]
0x180015f1c  jmp     loc_180015FAF
0x180015f21  xor     ebp, ebp
0x180015f23  test    eax, eax
0x180015f25  jz      short loc_180015F61
0x180015f27  lea     rcx, ds:0[rbp*8]
0x180015f2f  add     rcx, rbp
0x180015f32  shl     rcx, 4
0x180015f36  add     rcx, [rdi+18h]
0x180015f3a  mov     [rdi+60h], rcx
0x180015f3e  mov     rcx, [rcx+8]; this
0x180015f42  test    rcx, rcx
0x180015f45  jz      loc_18001603E
0x180015f4b  call    ?Run@Troubleshooter@@QEAAJXZ; Troubleshooter::Run(void)
0x180015f50  mov     ebx, eax
0x180015f52  test    eax, eax
0x180015f54  js      loc_180016033
0x180015f5a  add     ebp, esi
0x180015f5c  cmp     ebp, [rdi+20h]
0x180015f5f  jb      short loc_180015F27
0x180015f61  mov     r14, [rsp+58h+arg_0]
0x180015f66  xor     ebp, ebp
0x180015f68  cmp     [rdi+20h], ebp
0x180015f6b  jbe     short loc_180015F99
0x180015f6d  lea     rcx, ds:0[rbp*8]
0x180015f75  mov     rdx, r14; struct IXMLDOMDocument2 *
0x180015f78  add     rcx, rbp
0x180015f7b  shl     rcx, 4
0x180015f7f  add     rcx, [rdi+18h]; this
0x180015f83  call    ?get_DiagnosisResult@Rootcause@@QEAAJPEAUIXMLDOMDocument2@@@Z; Rootcause::get_DiagnosisResult(IXMLDOMDocument2 *)
0x180015f88  mov     ebx, eax
0x180015f8a  test    eax, eax
0x180015f8c  js      loc_180016069
0x180015f92  add     ebp, esi
0x180015f94  cmp     ebp, [rdi+20h]
0x180015f97  jb      short loc_180015F6D
0x180015f99  mov     rax, [r14]
0x180015f9c  mov     rcx, r14
0x180015f9f  mov     [r15], r14
0x180015fa2  mov     rax, [rax+8]
0x180015fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fab  test    ebx, ebx
0x180015fad  jns     short loc_180016008
0x180015faf  lea     r15, [rdi+80h]
0x180015fb6  mov     rcx, [r15]
0x180015fb9  test    rcx, rcx
0x180015fbc  jz      short loc_180015FD1
0x180015fbe  mov     rax, [rcx]
0x180015fc1  mov     rax, [rax+10h]
0x180015fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fca  mov     qword ptr [r15], 0
0x180015fd1  mov     rdx, r15; struct IXMLDOMDocument2 **
0x180015fd4  lea     rcx, aXmlVersion10En_20; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x180015fdb  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x180015fe0  xor     ebp, ebp
0x180015fe2  cmp     [rdi+20h], ebp
0x180015fe5  jbe     short loc_180016008
0x180015fe7  lea     rcx, ds:0[rbp*8]
0x180015fef  mov     edx, esi; int
0x180015ff1  add     rcx, rbp
0x180015ff4  shl     rcx, 4
0x180015ff8  add     rcx, [rdi+18h]; this
0x180015ffc  call    ?Reset@Rootcause@@QEAAJH@Z; Rootcause::Reset(int)
0x180016001  add     ebp, esi
0x180016003  cmp     ebp, [rdi+20h]
0x180016006  jb      short loc_180015FE7
0x180016008  mov     qword ptr [rdi+60h], 0
0x180016010  test    r14, r14
0x180016013  jz      short loc_180016024
0x180016015  mov     rax, [r14]
0x180016018  mov     rcx, r14
0x18001601b  mov     rax, [rax+10h]
0x18001601f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016024  mov     eax, ebx
0x180016026  add     rsp, 28h
0x18001602a  pop     r15
0x18001602c  pop     r14
0x18001602e  pop     rdi
0x18001602f  pop     rsi
0x180016030  pop     rbp
0x180016031  pop     rbx
0x180016032  retn
0x180016033  mov     r8d, 0B7h
0x180016039  mov     r9d, eax
0x18001603c  jmp     short loc_18001604D
0x18001603e  mov     r9d, 80004003h; int
0x180016044  mov     r8d, 0B0h; int
0x18001604a  mov     ebx, r9d
0x18001604d  lea     rdx, aRootcauseDiagn; "Rootcause::Diagnose"
0x180016054  mov     ecx, esi; Level
0x180016056  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001605b  mov     r9d, ebx
0x18001605e  mov     r8d, 0C2h
0x180016064  jmp     loc_180015F09
0x180016069  mov     r9d, eax
0x18001606c  mov     r8d, 0CCh
0x180016072  jmp     loc_180015E62
```

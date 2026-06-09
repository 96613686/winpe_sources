# ATL::CComPolyObject<ATL::CAxHostWindow>::Release(void)

- ea: `0x140007ba0`
- end: `0x140007c24`
- name: `?Release@?$CComPolyObject@VCAxHostWindow@ATL@@@ATL@@UEAAKXZ`
- size: `132`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001008`
- `0x140002238`
- `0x140007ba0`
- `0x140007c2c`
- `0x14000c818`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<ATL::CAxHostWindow>::Release(_DWORD *a1)
{
  int v1; // esi
  unsigned int v3; // esi
  CExeModule *v4; // rcx

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[2] = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_1400153D8);
      if ( a1 )
      {
        a1[2] = 1;
        *(_QWORD *)a1 = &ATL::CComPolyObject<ATL::CAxHostWindow>::`vftable';
        ATL::CAxHostWindow::ReleaseAll((ATL::CAxHostWindow *)(a1 + 4));
        CExeModule::Unlock(v4);
        ATL::CAxHostWindow::~CAxHostWindow((ATL::CAxHostWindow *)(a1 + 4));
        operator delete(a1);
      }
      CExeModule::Unlock((CExeModule *)a1);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140007ba0  mov     [rsp+arg_0], rbx
0x140007ba5  mov     [rsp+arg_8], rsi
0x140007baa  push    rdi
0x140007bab  sub     rsp, 20h
0x140007baf  mov     esi, [rcx+8]
0x140007bb2  mov     rdi, rcx
0x140007bb5  cmp     esi, 7FFFFFFFh
0x140007bbb  jnz     short loc_140007BC4
0x140007bbd  mov     esi, 7FFFFFFEh
0x140007bc2  jmp     short loc_140007C12
0x140007bc4  sub     esi, 1
0x140007bc7  mov     [rcx+8], esi
0x140007bca  jnz     short loc_140007C12
0x140007bcc  lock inc cs:dword_1400153D8
0x140007bd3  test    rdi, rdi
0x140007bd6  jz      short loc_140007C0D
0x140007bd8  lea     rax, ??_7?$CComPolyObject@VCAxHostWindow@ATL@@@ATL@@6B@; const ATL::CComPolyObject<ATL::CAxHostWindow>::`vftable'
0x140007bdf  mov     dword ptr [rcx+8], 1
0x140007be6  mov     [rcx], rax
0x140007be9  add     rcx, 10h; this
0x140007bed  call    ?ReleaseAll@CAxHostWindow@ATL@@QEAAXXZ; ATL::CAxHostWindow::ReleaseAll(void)
0x140007bf2  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140007bf7  lea     rcx, [rdi+10h]; this
0x140007bfb  call    ??1CAxHostWindow@ATL@@QEAA@XZ; ATL::CAxHostWindow::~CAxHostWindow(void)
0x140007c00  mov     edx, 168h; unsigned __int64
0x140007c05  mov     rcx, rdi; void *
0x140007c08  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007c0d  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140007c12  mov     rbx, [rsp+28h+arg_0]
0x140007c17  mov     eax, esi
0x140007c19  mov     rsi, [rsp+28h+arg_8]
0x140007c1e  add     rsp, 20h
0x140007c22  pop     rdi
0x140007c23  retn
```

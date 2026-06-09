# DVRCreateDVRFileSource

- ea: `0x1800077c0`
- end: `0x18000789a`
- name: `DVRCreateDVRFileSource`
- size: `218`
- prototype: `__int64 __fastcall(HKEY, HKEY, unsigned int, void **, int, __int64, struct IDVRSourceAdviseSink *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800011a0`
- `0x1800052ac`
- `0x1800077c0`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall DVRCreateDVRFileSource(
        HKEY a1,
        HKEY a2,
        unsigned int a3,
        void **a4,
        int a5,
        _QWORD *a6,
        struct IDVRSourceAdviseSink *a7)
{
  CDVRSource *v12; // rax
  CDVRSource *v13; // rax
  CDVRSource *v14; // rdi
  int v15; // ebx
  int v16[14]; // [rsp+40h] [rbp-38h] BYREF

  v16[0] = 0;
  if ( !a6 )
    return 2147500035LL;
  *a6 = 0;
  v12 = (CDVRSource *)operator new(0xF0u);
  if ( !v12 )
    return 2147942414LL;
  v13 = CDVRSource::CDVRSource(v12, a1, a2, a3, a4, a5, v16, a7);
  v14 = v13;
  if ( !v13 )
    return 2147942414LL;
  v15 = v16[0];
  if ( v16[0] < 0
    || (v15 = (**(__int64 (__fastcall ***)(CDVRSource *, GUID *, _QWORD *))v13)(v13, &IID_IDVRFileSource, a6), v15 < 0) )
  {
    (*(void (__fastcall **)(CDVRSource *, __int64))(*(_QWORD *)v14 + 112LL))(v14, 1);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800077c0  push    rbx
0x1800077c2  push    rbp
0x1800077c3  push    rsi
0x1800077c4  push    rdi
0x1800077c5  push    r14
0x1800077c7  sub     rsp, 50h
0x1800077cb  mov     rsi, [rsp+78h+arg_28]
0x1800077d3  mov     rbx, r9
0x1800077d6  mov     [rsp+78h+var_38], 0
0x1800077de  mov     edi, r8d
0x1800077e1  mov     rbp, rdx
0x1800077e4  mov     r14, rcx
0x1800077e7  test    rsi, rsi
0x1800077ea  jnz     short loc_1800077F6
0x1800077ec  mov     eax, 80004003h
0x1800077f1  jmp     loc_18000788F
0x1800077f6  mov     ecx, 0F0h; Size
0x1800077fb  mov     qword ptr [rsi], 0
0x180007802  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007807  test    rax, rax
0x18000780a  jz      short loc_18000788A
0x18000780c  mov     rcx, [rsp+78h+arg_30]
0x180007814  mov     r9d, edi; unsigned int
0x180007817  mov     [rsp+78h+var_40], rcx; struct IDVRSourceAdviseSink *
0x18000781c  mov     r8, rbp; HKEY
0x18000781f  lea     rcx, [rsp+78h+var_38]
0x180007824  mov     rdx, r14; HKEY
0x180007827  mov     [rsp+78h+var_48], rcx; int *
0x18000782c  mov     ecx, [rsp+78h+arg_20]
0x180007833  mov     [rsp+78h+var_50], ecx; int
0x180007837  mov     rcx, rax; this
0x18000783a  mov     [rsp+78h+var_58], rbx; void **
0x18000783f  call    ??0CDVRSource@@QEAA@PEAUHKEY__@@0KPEAPEAXHPEAJPEAUIDVRSourceAdviseSink@@@Z; CDVRSource::CDVRSource(HKEY__ *,HKEY__ *,ulong,void * *,int,long *,IDVRSourceAdviseSink *)
0x180007844  mov     rdi, rax
0x180007847  test    rax, rax
0x18000784a  jz      short loc_18000788A
0x18000784c  mov     ebx, [rsp+78h+var_38]
0x180007850  test    ebx, ebx
0x180007852  js      short loc_180007872
0x180007854  mov     rcx, [rax]
0x180007857  lea     rdx, IID_IDVRFileSource
0x18000785e  mov     r8, rsi
0x180007861  mov     rax, [rcx]
0x180007864  mov     rcx, rdi
0x180007867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000786c  mov     ebx, eax
0x18000786e  test    eax, eax
0x180007870  jns     short loc_180007886
0x180007872  mov     rcx, [rdi]
0x180007875  mov     edx, 1
0x18000787a  mov     rax, [rcx+70h]
0x18000787e  mov     rcx, rdi
0x180007881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007886  mov     eax, ebx
0x180007888  jmp     short loc_18000788F
0x18000788a  mov     eax, 8007000Eh
0x18000788f  add     rsp, 50h
0x180007893  pop     r14
0x180007895  pop     rdi
0x180007896  pop     rsi
0x180007897  pop     rbp
0x180007898  pop     rbx
0x180007899  retn
```

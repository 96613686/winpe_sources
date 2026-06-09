# CWshNetwork::Create(IUnknown *)

- ea: `0x180007f00`
- end: `0x180007f87`
- name: `?Create@CWshNetwork@@SAPEAUIUnknown@@PEAU2@@Z`
- size: `135`
- prototype: `struct IUnknown *__fastcall(struct IUnknown *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800060e4`
- `0x180007f00`

## pseudocode

```c
struct IUnknown *__fastcall CWshNetwork::Create(struct IUnknownVtbl *a1)
{
  struct IUnknown *v2; // rax

  v2 = (struct IUnknown *)operator new(0x48u);
  if ( v2 )
  {
    v2[2].lpVtbl = (struct IUnknownVtbl *)&CUnknown::`vftable';
    if ( !a1 )
      a1 = (struct IUnknownVtbl *)&v2[5];
    LODWORD(v2[6].lpVtbl) = 1;
    v2[5].lpVtbl = (struct IUnknownVtbl *)&CUnknown::InnerUnknown::`vftable';
    v2[3].lpVtbl = a1;
    v2[4].lpVtbl = (struct IUnknownVtbl *)v2;
    _InterlockedIncrement(&Global::g_cObjects);
    LOBYTE(v2[8].lpVtbl) = 0;
    v2[7].lpVtbl = (struct IUnknownVtbl *)&TaUser_DescCWshNetwork;
    v2->lpVtbl = (struct IUnknownVtbl *)&CWshNetwork::`vftable'{for `IWshNetwork2'};
    v2[1].lpVtbl = (struct IUnknownVtbl *)&CWshEnvProcess::`vftable'{for `IProvideClassInfo'};
    v2[2].lpVtbl = (struct IUnknownVtbl *)&CWshNetwork::`vftable'{for `CAutoObj'};
  }
  return v2 + 5;
}

```

## disassembly

```asm
0x180007f00  push    rbx
0x180007f02  sub     rsp, 20h
0x180007f06  mov     rbx, rcx
0x180007f09  mov     ecx, 48h ; 'H'; Size
0x180007f0e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007f13  test    rax, rax
0x180007f16  jz      short loc_180007F7D
0x180007f18  lea     rdx, [rax+28h]
0x180007f1c  test    rbx, rbx
0x180007f1f  lea     rcx, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x180007f26  mov     [rax+10h], rcx
0x180007f2a  cmovz   rbx, rdx
0x180007f2e  mov     dword ptr [rdx+8], 1
0x180007f35  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x180007f3c  mov     [rdx], rcx
0x180007f3f  mov     [rax+18h], rbx
0x180007f43  mov     [rax+20h], rax
0x180007f47  lock inc cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x180007f4e  mov     byte ptr [rax+40h], 0
0x180007f52  lea     rcx, ?TaUser_DescCWshNetwork@@3UTaDescDispatch@@A; TaDescDispatch TaUser_DescCWshNetwork
0x180007f59  mov     [rax+38h], rcx
0x180007f5d  lea     rcx, ??_7CWshNetwork@@6BIWshNetwork2@@@; const CWshNetwork::`vftable'{for `IWshNetwork2'}
0x180007f64  mov     [rax], rcx
0x180007f67  lea     rcx, ??_7CWshEnvProcess@@6BIProvideClassInfo@@@; const CWshEnvProcess::`vftable'{for `IProvideClassInfo'}
0x180007f6e  mov     [rax+8], rcx
0x180007f72  lea     rcx, ??_7CWshNetwork@@6BCAutoObj@@@; const CWshNetwork::`vftable'{for `CAutoObj'}
0x180007f79  mov     [rax+10h], rcx
0x180007f7d  add     rax, 28h ; '('
0x180007f81  add     rsp, 20h
0x180007f85  pop     rbx
0x180007f86  retn
```

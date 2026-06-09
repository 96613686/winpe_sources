# CWbemPathCracker::~CWbemPathCracker(void)

- ea: `0x18001643c`
- end: `0x18001647d`
- name: `??1CWbemPathCracker@@UEAA@XZ`
- size: `65`
- prototype: `void __fastcall(CWbemPathCracker *__hidden this)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d490`
- `0x18001ff50`
- `0x1800201f0`
- `0x1800298b0`
- `0x18002c860`
- `0x18002f4c0`
- `0x1800317c0`
- `0x180032c08`
- `0x180032db4`
- `0x180033220`
- `0x180034440`
- `0x1800344f0`
- `0x180034590`
- `0x180034ed0`
- `0x1800357a4`
- `0x180035806`
- `0x180035928`
- `0x18003595e`
- `0x180035a5b`

## callees

- `0x18001643c`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001645a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001645a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWbemPathCracker::~CWbemPathCracker(BSTR *this)
{
  BSTR v2; // rcx

  *this = (BSTR)&CWbemPathCracker::`vftable';
  _InterlockedDecrement(&g_cObj);
  SysFreeString(this[2]);
  v2 = this[1];
  if ( v2 )
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v2 + 16LL))(v2);
}

```

## disassembly

```asm
0x18001643c  push    rbx
0x18001643e  sub     rsp, 20h
0x180016442  mov     rbx, rcx
0x180016445  lea     rax, ??_7CWbemPathCracker@@6B@; const CWbemPathCracker::`vftable'
0x18001644c  mov     [rcx], rax
0x18001644f  lock dec cs:?g_cObj@@3JA; long g_cObj
0x180016456  mov     rcx, [rcx+10h]; bstrString
0x18001645a  call    cs:__imp_SysFreeString
0x180016460  nop
0x180016461  mov     rcx, [rbx+8]
0x180016465  test    rcx, rcx
0x180016468  jz      short loc_180016477
0x18001646a  mov     rax, [rcx]
0x18001646d  mov     rax, [rax+10h]
0x180016471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016476  nop
0x180016477  add     rsp, 20h
0x18001647b  pop     rbx
0x18001647c  retn
```

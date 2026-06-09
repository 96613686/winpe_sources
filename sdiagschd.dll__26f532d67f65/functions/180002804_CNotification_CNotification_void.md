# CNotification::~CNotification(void)

- ea: `0x180002804`
- end: `0x180002848`
- name: `??1CNotification@@QEAA@XZ`
- size: `68`
- prototype: `void __fastcall(CNotification *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004258`
- `0x18000586c`

## callees

- `0x180002804`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002816`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002830`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002816`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180002830`

## pseudocode

```c
void __fastcall CNotification::~CNotification(CNotification *this)
{
  SAFEARRAY *v2; // rcx
  SAFEARRAY *v3; // rcx

  v2 = (SAFEARRAY *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    SafeArrayDestroy(v2);
    *((_QWORD *)this + 2) = 0;
  }
  v3 = (SAFEARRAY *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    SafeArrayDestroy(v3);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180002804  push    rbx
0x180002806  sub     rsp, 20h
0x18000280a  mov     rbx, rcx
0x18000280d  mov     rcx, [rcx+10h]; psa
0x180002811  test    rcx, rcx
0x180002814  jz      short loc_180002827
0x180002816  call    cs:__imp_SafeArrayDestroy
0x18000281d  nop     dword ptr [rax+rax+00h]
0x180002822  and     qword ptr [rbx+10h], 0
0x180002827  mov     rcx, [rbx+18h]; psa
0x18000282b  test    rcx, rcx
0x18000282e  jz      short loc_180002841
0x180002830  call    cs:__imp_SafeArrayDestroy
0x180002837  nop     dword ptr [rax+rax+00h]
0x18000283c  and     qword ptr [rbx+18h], 0
0x180002841  add     rsp, 20h
0x180002845  pop     rbx
0x180002846  retn
```

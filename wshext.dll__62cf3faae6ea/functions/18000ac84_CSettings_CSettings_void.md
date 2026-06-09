# CSettings::CSettings(void)

- ea: `0x18000ac84`
- end: `0x18000acc7`
- name: `??0CSettings@@QEAA@XZ`
- size: `67`
- prototype: `CSettings *__fastcall(CSettings *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180006160`
- `0x180006440`
- `0x180007264`

## import_xrefs

- `KERNEL32!GetACP` at `0x18000ac99`
- `KERNEL32!GetACP` at `0x18000ac99`

## pseudocode

```c
CSettings *__fastcall CSettings::CSettings(CSettings *this)
{
  UINT ACP; // eax
  CSettings *result; // rax

  *((_BYTE *)this + 6) = 1;
  *(_DWORD *)this = 0;
  ACP = GetACP();
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 14) = 0;
  *((_DWORD *)this + 3) = ACP;
  result = this;
  *((_DWORD *)this + 6) = 87;
  *((_WORD *)this + 2) = 0;
  *(_WORD *)((char *)this + 7) = 0;
  return result;
}

```

## disassembly

```asm
0x18000ac84  mov     [rsp+arg_0], rbx
0x18000ac89  push    rdi
0x18000ac8a  sub     rsp, 20h
0x18000ac8e  xor     edi, edi
0x18000ac90  mov     byte ptr [rcx+6], 1
0x18000ac94  mov     [rcx], edi
0x18000ac96  mov     rbx, rcx
0x18000ac99  call    cs:__imp_GetACP
0x18000ac9f  mov     [rbx+10h], rdi
0x18000aca3  mov     [rbx+1Ch], di
0x18000aca7  mov     [rbx+0Ch], eax
0x18000acaa  mov     rax, rbx
0x18000acad  mov     dword ptr [rbx+18h], 57h ; 'W'
0x18000acb4  mov     [rbx+4], di
0x18000acb8  mov     [rbx+7], di
0x18000acbc  mov     rbx, [rsp+28h+arg_0]
0x18000acc1  add     rsp, 20h
0x18000acc5  pop     rdi
0x18000acc6  retn
```

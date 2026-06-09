# tpm12class::TpmDataObject::UpdateStore(tpm12class::TpmDataObject *)

- ea: `0x14000cfbc`
- end: `0x14000d016`
- name: `?UpdateStore@TpmDataObject@tpm12class@@IEAAXPEAV12@@Z`
- size: `90`
- prototype: `void __fastcall(tpm12class::TpmDataObject *__hidden this, struct tpm12class::TpmDataObject *)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000cf48`
- `0x140031ea0`
- `0x140032164`

## callees

- `0x14000cfbc`
- `0x14000d090`

## pseudocode

```c
void __fastcall tpm12class::TpmDataObject::UpdateStore(
        tpm12class::TpmDataObject *this,
        struct tpm12class::TpmDataObject *a2)
{
  if ( a2 )
  {
    *((_QWORD *)a2 + 1) = *((_QWORD *)this + 1);
    *((_DWORD *)a2 + 6) = *((_DWORD *)this + 6);
    *((_DWORD *)a2 + 4) = *((_DWORD *)this + 4);
    *((_DWORD *)a2 + 5) = *((_DWORD *)this + 5);
    *((_BYTE *)a2 + 48) = *((_BYTE *)this + 48);
    *((_QWORD *)a2 + 4) = *((_QWORD *)this + 4);
    *((_DWORD *)a2 + 10) = *((_DWORD *)this + 10);
    *((_DWORD *)a2 + 11) = *((_DWORD *)this + 11);
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 4) = 0;
  }
  tpm12class::TpmDataObject::Clear(this, 1u);
}

```

## disassembly

```asm
0x14000cfbc  sub     rsp, 28h
0x14000cfc0  test    rdx, rdx
0x14000cfc3  jz      short loc_14000D009
0x14000cfc5  mov     rax, [rcx+8]
0x14000cfc9  mov     [rdx+8], rax
0x14000cfcd  mov     eax, [rcx+18h]
0x14000cfd0  mov     [rdx+18h], eax
0x14000cfd3  mov     eax, [rcx+10h]
0x14000cfd6  mov     [rdx+10h], eax
0x14000cfd9  mov     eax, [rcx+14h]
0x14000cfdc  mov     [rdx+14h], eax
0x14000cfdf  mov     al, [rcx+30h]
0x14000cfe2  mov     [rdx+30h], al
0x14000cfe5  mov     rax, [rcx+20h]
0x14000cfe9  mov     [rdx+20h], rax
0x14000cfed  mov     eax, [rcx+28h]
0x14000cff0  mov     [rdx+28h], eax
0x14000cff3  mov     eax, [rcx+2Ch]
0x14000cff6  mov     [rdx+2Ch], eax
0x14000cff9  mov     qword ptr [rcx+8], 0
0x14000d001  mov     qword ptr [rcx+20h], 0
0x14000d009  mov     dl, 1; unsigned __int8
0x14000d00b  call    ?Clear@TpmDataObject@tpm12class@@MEAAJE@Z; tpm12class::TpmDataObject::Clear(uchar)
0x14000d010  add     rsp, 28h
0x14000d014  retn
```

# CShareSecurityInformation::GetShareInfoThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18000b0b0`
- end: `0x18000b13b`
- name: `?GetShareInfoThread@CShareSecurityInformation@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `139`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b0b0`
- `0x18000b144`
- `0x18001e010`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18000b0cb`
- `msvcrt!wcsnlen` at `0x18000b0cb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b120`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b120`

## pseudocode

```c
void __fastcall CShareSecurityInformation::GetShareInfoThread(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WORK Work)
{
  _WORD *v4; // rax
  const unsigned __int16 *v5; // rcx
  int ShareInfoWMI; // eax
  void *v7; // rcx
  signed __int32 v8[10]; // [rsp+0h] [rbp-28h] BYREF
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  if ( wcsnlen(*((const wchar_t **)Context + 2), 3u) != 3
    || (v4 = (_WORD *)*((_QWORD *)Context + 2), *v4 != 92)
    || (v5 = v4 + 2, v4[1] != 92) )
  {
    v5 = (const unsigned __int16 *)*((_QWORD *)Context + 2);
  }
  ShareInfoWMI = CShareSecurityInformation::GetShareInfoWMI(v5, *((const unsigned __int16 **)Context + 1), &v9);
  if ( ShareInfoWMI >= 0 )
  {
    *((_QWORD *)Context + 32) = v9;
    _InterlockedOr(v8, 0);
  }
  v7 = (void *)*((_QWORD *)Context + 29);
  *((_DWORD *)Context + 60) = ShareInfoWMI;
  SetEvent(v7);
  (*(void (__fastcall **)(PVOID))(*(_QWORD *)Context + 16LL))(Context);
}

```

## disassembly

```asm
0x18000b0b0  push    rbx
0x18000b0b2  sub     rsp, 20h
0x18000b0b6  mov     rbx, rdx
0x18000b0b9  mov     [rsp+28h+arg_8], 0
0x18000b0c2  mov     edx, 3; MaxCount
0x18000b0c7  mov     rcx, [rbx+10h]; Source
0x18000b0cb  call    cs:__imp_wcsnlen
0x18000b0d1  cmp     rax, 3
0x18000b0d5  jnz     short loc_18000B0EC
0x18000b0d7  mov     rax, [rbx+10h]
0x18000b0db  cmp     word ptr [rax], 5Ch ; '\'
0x18000b0df  jnz     short loc_18000B0EC
0x18000b0e1  cmp     word ptr [rax+2], 5Ch ; '\'
0x18000b0e6  lea     rcx, [rax+4]
0x18000b0ea  jz      short loc_18000B0F0
0x18000b0ec  mov     rcx, [rbx+10h]; unsigned __int16 *
0x18000b0f0  mov     rdx, [rbx+8]; unsigned __int16 *
0x18000b0f4  lea     r8, [rsp+28h+arg_8]; void **
0x18000b0f9  call    ?GetShareInfoWMI@CShareSecurityInformation@@CAJPEBG0PEAPEAX@Z; CShareSecurityInformation::GetShareInfoWMI(ushort const *,ushort const *,void * *)
0x18000b0fe  test    eax, eax
0x18000b100  js      short loc_18000B113
0x18000b102  mov     rcx, [rsp+28h+arg_8]
0x18000b107  mov     [rbx+100h], rcx
0x18000b10e  lock or [rsp+28h+var_28], 0
0x18000b113  mov     rcx, [rbx+0E8h]; hEvent
0x18000b11a  mov     [rbx+0F0h], eax
0x18000b120  call    cs:__imp_SetEvent
0x18000b126  mov     rax, [rbx]
0x18000b129  mov     rcx, rbx
0x18000b12c  mov     rax, [rax+10h]
0x18000b130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b135  add     rsp, 20h
0x18000b139  pop     rbx
0x18000b13a  retn
```

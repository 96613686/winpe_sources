# TmpDeleteTransactionManager

- ea: `0x140015920`
- end: `0x140015a47`
- name: `TmpDeleteTransactionManager`
- size: `295`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000c7e8`
- `0x140015920`

## import_xrefs

- `CLFS!ClfsDeleteMarshallingArea` at `0x140015971`
- `CLFS!ClfsDeleteMarshallingArea` at `0x140015971`
- `CLFS!ClfsCloseLogFileObject` at `0x140015990`
- `CLFS!ClfsCloseLogFileObject` at `0x140015990`
- `CLFS!ClfsMgmtDeregisterManagedClient` at `0x1400159ab`
- `CLFS!ClfsMgmtDeregisterManagedClient` at `0x1400159ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015a0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015a0b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400159d1`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400159d1`
- `ntoskrnl!ExDeleteResourceLite` at `0x140015a23`
- `ntoskrnl!ExDeleteResourceLite` at `0x140015a23`

## pseudocode

```c
void __fastcall TmpDeleteTransactionManager(__int64 a1)
{
  void *v2; // rdi
  void *v3; // rcx
  FILE_OBJECT *v4; // rcx
  _QWORD *v5; // rdi
  _QWORD *v6; // rax
  _QWORD *v7; // rdx
  _QWORD *v8; // rcx

  if ( *(_DWORD *)(a1 + 64) )
  {
    v2 = 0;
    _InterlockedOr((volatile signed __int32 *)(a1 + 128), 0x80000000);
    TmpTmOffline();
    if ( *(_QWORD *)(a1 + 168) )
    {
      v2 = *(void **)(a1 + 168);
      *(_QWORD *)(a1 + 168) = 0;
    }
    v3 = *(void **)(a1 + 160);
    if ( v3 )
    {
      ClfsDeleteMarshallingArea(v3);
      *(_QWORD *)(a1 + 160) = 0;
    }
    v4 = *(FILE_OBJECT **)(a1 + 152);
    if ( v4 )
    {
      ClfsCloseLogFileObject(v4);
      *(_QWORD *)(a1 + 152) = 0;
    }
    if ( v2 )
      ClfsMgmtDeregisterManagedClient(v2);
    if ( (*(_DWORD *)(a1 + 128) & 1) == 0 && *(_QWORD *)(a1 + 144) )
      RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 136));
    v5 = *(_QWORD **)(a1 + 912);
    while ( v5 != (_QWORD *)(a1 + 912) )
    {
      v6 = (_QWORD *)*v5;
      if ( *(_QWORD **)(*v5 + 8LL) != v5 || (v7 = (_QWORD *)v5[1], (_QWORD *)*v7 != v5) )
        __fastfail(3u);
      *v7 = v6;
      v8 = v5 - 1;
      v6[1] = v7;
      v5 = v6;
      ExFreePoolWithTag(v8, 0);
    }
    ExDeleteResourceLite((PERESOURCE)(a1 + 784));
  }
}

```

## disassembly

```asm
0x140015920  mov     [rsp+arg_0], rbx
0x140015925  mov     [rsp+arg_8], rsi
0x14001592a  push    rdi
0x14001592b  sub     rsp, 20h
0x14001592f  xor     esi, esi
0x140015931  mov     rbx, rcx
0x140015934  cmp     [rcx+40h], esi
0x140015937  jz      loc_140015A2F
0x14001593d  mov     edi, esi
0x14001593f  lock or dword ptr [rcx+80h], 80000000h
0x14001594a  call    TmpTmOffline
0x14001594f  mov     rax, [rbx+0A8h]
0x140015956  test    rax, rax
0x140015959  jz      short loc_140015965
0x14001595b  mov     rdi, rax
0x14001595e  mov     [rbx+0A8h], rsi
0x140015965  mov     rcx, [rbx+0A0h]; pvMarshalContext
0x14001596c  test    rcx, rcx
0x14001596f  jz      short loc_140015984
0x140015971  call    cs:__imp_ClfsDeleteMarshallingArea
0x140015978  nop     dword ptr [rax+rax+00h]
0x14001597d  mov     [rbx+0A0h], rsi
0x140015984  mov     rcx, [rbx+98h]; plfoLog
0x14001598b  test    rcx, rcx
0x14001598e  jz      short loc_1400159A3
0x140015990  call    cs:__imp_ClfsCloseLogFileObject
0x140015997  nop     dword ptr [rax+rax+00h]
0x14001599c  mov     [rbx+98h], rsi
0x1400159a3  test    rdi, rdi
0x1400159a6  jz      short loc_1400159B7
0x1400159a8  mov     rcx, rdi; ClientCookie
0x1400159ab  call    cs:__imp_ClfsMgmtDeregisterManagedClient
0x1400159b2  nop     dword ptr [rax+rax+00h]
0x1400159b7  mov     eax, [rbx+80h]
0x1400159bd  test    al, 1
0x1400159bf  jnz     short loc_1400159DD
0x1400159c1  cmp     [rbx+90h], rsi
0x1400159c8  jz      short loc_1400159DD
0x1400159ca  lea     rcx, [rbx+88h]; UnicodeString
0x1400159d1  call    cs:__imp_RtlFreeUnicodeString
0x1400159d8  nop     dword ptr [rax+rax+00h]
0x1400159dd  lea     rsi, [rbx+390h]
0x1400159e4  mov     rdi, [rsi]
0x1400159e7  jmp     short loc_140015A17
0x1400159e9  mov     rax, [rdi]
0x1400159ec  cmp     [rax+8], rdi
0x1400159f0  jnz     short loc_140015A40
0x1400159f2  mov     rdx, [rdi+8]
0x1400159f6  cmp     [rdx], rdi
0x1400159f9  jnz     short loc_140015A40
0x1400159fb  mov     [rdx], rax
0x1400159fe  lea     rcx, [rdi-8]; P
0x140015a02  mov     [rax+8], rdx
0x140015a06  mov     rdi, rax
0x140015a09  xor     edx, edx; Tag
0x140015a0b  call    cs:__imp_ExFreePoolWithTag
0x140015a12  nop     dword ptr [rax+rax+00h]
0x140015a17  cmp     rdi, rsi
0x140015a1a  jnz     short loc_1400159E9
0x140015a1c  lea     rcx, [rbx+310h]; Resource
0x140015a23  call    cs:__imp_ExDeleteResourceLite
0x140015a2a  nop     dword ptr [rax+rax+00h]
0x140015a2f  mov     rbx, [rsp+28h+arg_0]
0x140015a34  mov     rsi, [rsp+28h+arg_8]
0x140015a39  add     rsp, 20h
0x140015a3d  pop     rdi
0x140015a3e  retn
0x140015a40  mov     ecx, 3
0x140015a45  int     29h; Win8: RtlFailFast(ecx)
```

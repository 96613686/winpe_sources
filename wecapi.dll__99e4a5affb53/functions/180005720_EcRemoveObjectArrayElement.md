# EcRemoveObjectArrayElement

- ea: `0x180005720`
- end: `0x1800057a3`
- name: `EcRemoveObjectArrayElement`
- size: `131`
- prototype: `BOOL __stdcall(EC_OBJECT_ARRAY_PROPERTY_HANDLE ObjectArray, DWORD ArrayIndex)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800027ec`
- `0x180005720`
- `0x1800073c4`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005786`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005786`

## pseudocode

```c
BOOL __stdcall EcRemoveObjectArrayElement(EC_OBJECT_ARRAY_PROPERTY_HANDLE ObjectArray, DWORD ArrayIndex)
{
  BOOL v3; // ebx
  __int64 v4; // rdx
  EventSourceCollection *v5; // rdi
  EventSourceCollection *v7; // [rsp+50h] [rbp+18h] BYREF

  v3 = 0;
  v7 = 0;
  GetClassifiedObject<EventSourceCollection>(ObjectArray, ArrayIndex, &v7);
  v4 = ArrayIndex;
  v5 = v7;
  EventSourceCollection::Remove(v7, v4);
  if ( v5 && _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(EventSourceCollection *, __int64))v5)(v5, 1);
  SetLastError(0);
  LOBYTE(v3) = 1;
  return v3;
}

```

## disassembly

```asm
0x180005720  mov     rax, rsp
0x180005723  mov     [rax+8], rbx
0x180005727  mov     [rax+10h], rsi
0x18000572b  push    rdi
0x18000572c  sub     rsp, 30h
0x180005730  mov     edi, edx
0x180005732  xor     ebx, ebx
0x180005734  mov     esi, ebx
0x180005736  mov     [rax+18h], rbx
0x18000573a  lea     r8, [rax+18h]
0x18000573e  call    ??$GetClassifiedObject@VEventSourceCollection@@@@YAXPEAXW4ObjectType@@AEAV?$AutoRef@VEventSourceCollection@@@wmi@@@Z; GetClassifiedObject<EventSourceCollection>(void *,ObjectType,wmi::AutoRef<EventSourceCollection> &)
0x180005743  mov     edx, edi; unsigned int
0x180005745  mov     rdi, [rsp+38h+arg_10]
0x18000574a  mov     rcx, rdi; this
0x18000574d  call    ?Remove@EventSourceCollection@@QEAAXK@Z; EventSourceCollection::Remove(ulong)
0x180005752  nop
0x180005753  test    rdi, rdi
0x180005756  jz      short loc_18000577C
0x180005758  or      eax, 0FFFFFFFFh
0x18000575b  lock xadd [rdi+8], eax
0x180005760  cmp     eax, 1
0x180005763  jnz     short loc_18000577C
0x180005765  test    rdi, rdi
0x180005768  jz      short loc_18000577C
0x18000576a  mov     rax, [rdi]
0x18000576d  lea     edx, [rbx+1]
0x180005770  mov     rcx, rdi
0x180005773  mov     rax, [rax]
0x180005776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000577b  nop
0x18000577c  jmp     short loc_180005784
0x18000577e  xor     ebx, ebx
0x180005780  mov     esi, dword ptr [rsp+38h+arg_10]
0x180005784  mov     ecx, esi; dwErrCode
0x180005786  call    cs:__imp_SetLastError
0x18000578c  test    esi, esi
0x18000578e  setz    bl
0x180005791  mov     eax, ebx
0x180005793  mov     rbx, [rsp+38h+arg_0]
0x180005798  mov     rsi, [rsp+38h+arg_8]
0x18000579d  add     rsp, 30h
0x1800057a1  pop     rdi
0x1800057a2  retn
```

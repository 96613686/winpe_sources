# IsAddAppContainerAccessWorkerPresent

- ea: `0x18000f61c`
- end: `0x18000f66a`
- name: `IsAddAppContainerAccessWorkerPresent`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012930`
- `0x180012980`
- `0x1800129e0`
- `0x180012bb0`
- `0x180012ce0`

## callees

- `0x18000f61c`
- `0x18000fae2`

## pseudocode

```c
char IsAddAppContainerAccessWorkerPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_1800294C0 == 1 )
    return 1;
  if ( dword_1800294C0 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L"BD", &v1) < 0 )
    return 0;
  result = v1;
  dword_1800294C0 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x18000f61c  sub     rsp, 28h
0x18000f620  mov     ecx, cs:dword_1800294C0
0x18000f626  sub     ecx, 1
0x18000f629  jz      short loc_18000F663
0x18000f62b  cmp     ecx, 1
0x18000f62e  jz      short loc_18000F65F
0x18000f630  lea     rdx, [rsp+28h+arg_0]
0x18000f635  mov     [rsp+28h+arg_0], 0
0x18000f63a  lea     rcx, aBd; "BD"
0x18000f641  call    ApiSetQueryApiSetPresence_0
0x18000f646  test    eax, eax
0x18000f648  js      short loc_18000F65F
0x18000f64a  mov     al, [rsp+28h+arg_0]
0x18000f64e  mov     cl, al
0x18000f650  neg     cl
0x18000f652  sbb     edx, edx
0x18000f654  add     edx, 2
0x18000f657  mov     cs:dword_1800294C0, edx
0x18000f65d  jmp     short loc_18000F665
0x18000f65f  xor     al, al
0x18000f661  jmp     short loc_18000F665
0x18000f663  mov     al, 1
0x18000f665  add     rsp, 28h
0x18000f669  retn
```

# IsUserServerDllInitializationExtPresent

- ea: `0x1800013ac`
- end: `0x1800013fa`
- name: `IsUserServerDllInitializationExtPresent`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001060`

## callees

- `0x1800013ac`
- `0x18000156b`

## pseudocode

```c
char IsUserServerDllInitializationExtPresent()
{
  char result; // al
  char v1; // [rsp+30h] [rbp+8h] BYREF

  if ( dword_180005590 == 1 )
    return 1;
  if ( dword_180005590 == 2 )
    return 0;
  v1 = 0;
  if ( (int)ApiSetQueryApiSetPresence_0(L":<", &v1) < 0 )
    return 0;
  result = v1;
  dword_180005590 = 2 - (v1 != 0);
  return result;
}

```

## disassembly

```asm
0x1800013ac  sub     rsp, 28h
0x1800013b0  mov     ecx, cs:dword_180005590
0x1800013b6  sub     ecx, 1
0x1800013b9  jz      short loc_1800013F3
0x1800013bb  cmp     ecx, 1
0x1800013be  jz      short loc_1800013EF
0x1800013c0  lea     rdx, [rsp+28h+arg_0]
0x1800013c5  mov     [rsp+28h+arg_0], 0
0x1800013ca  lea     rcx, asc_180003010; ":<"
0x1800013d1  call    ApiSetQueryApiSetPresence_0
0x1800013d6  test    eax, eax
0x1800013d8  js      short loc_1800013EF
0x1800013da  mov     al, [rsp+28h+arg_0]
0x1800013de  mov     cl, al
0x1800013e0  neg     cl
0x1800013e2  sbb     edx, edx
0x1800013e4  add     edx, 2
0x1800013e7  mov     cs:dword_180005590, edx
0x1800013ed  jmp     short loc_1800013F5
0x1800013ef  xor     al, al
0x1800013f1  jmp     short loc_1800013F5
0x1800013f3  mov     al, 1
0x1800013f5  add     rsp, 28h
0x1800013f9  retn
```

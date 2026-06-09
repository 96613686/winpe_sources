# SdbpGetPathSystem

- ea: `0x1400134e0`
- end: `0x140013576`
- name: `SdbpGetPathSystem`
- size: `150`
- prototype: `__int64 __fastcall(_WORD *, __int64, _WORD *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000f28c`
- `0x14001008c`
- `0x1400134e0`
- `0x14001357c`

## string_xrefs

- `0x140013549`: `AslEnvGetSystem32DirPathBuf failed [%x]`
- `0x140013556`: `SdbpGetPathSystem`

## pseudocode

```c
__int64 __fastcall SdbpGetPathSystem(_WORD *a1, __int64 a2, _WORD *a3, __int64 a4)
{
  int ProcessHostGuestArchitectures; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  __int64 v10; // r8
  __int64 v12; // [rsp+20h] [rbp-48h]
  __int16 v13[2]; // [rsp+30h] [rbp-38h] BYREF
  __int16 v14[26]; // [rsp+34h] [rbp-34h] BYREF

  v14[0] = 0;
  v13[0] = 0;
  ProcessHostGuestArchitectures = SdbpGetProcessHostGuestArchitectures(v14, v13, a4);
  v8 = ProcessHostGuestArchitectures;
  if ( ProcessHostGuestArchitectures < 0 )
  {
    v9 = "SdbpGetProcessHostGuestArchitectures failed [%x]";
    v10 = 1054;
LABEL_5:
    LODWORD(v12) = ProcessHostGuestArchitectures;
    AslLogCallPrintf(1, "SdbpGetPathSystem", v10, v9, v12);
    return v8;
  }
  ProcessHostGuestArchitectures = AslEnvGetSystem32DirPathBuf(a1, a2, a3, v14[0], v13);
  v8 = ProcessHostGuestArchitectures;
  if ( ProcessHostGuestArchitectures < 0 )
  {
    v9 = "AslEnvGetSystem32DirPathBuf failed [%x]";
    v10 = 1060;
    goto LABEL_5;
  }
  return v8;
}

```

## disassembly

```asm
0x1400134e0  push    rbx
0x1400134e2  push    rbp
0x1400134e3  push    rsi
0x1400134e4  push    rdi
0x1400134e5  sub     rsp, 48h
0x1400134e9  xor     eax, eax
0x1400134eb  mov     rdi, r8
0x1400134ee  mov     rsi, rdx
0x1400134f1  mov     [rsp+68h+var_34], ax
0x1400134f6  mov     rbp, rcx
0x1400134f9  mov     [rsp+68h+var_38], ax
0x1400134fe  mov     r8, r9
0x140013501  lea     rdx, [rsp+68h+var_38]
0x140013506  lea     rcx, [rsp+68h+var_34]
0x14001350b  call    SdbpGetProcessHostGuestArchitectures
0x140013510  mov     ebx, eax
0x140013512  test    eax, eax
0x140013514  jns     short loc_140013525
0x140013516  lea     r9, aSdbpgetprocess; "SdbpGetProcessHostGuestArchitectures fa"...
0x14001351d  mov     r8d, 41Eh
0x140013523  jmp     short loc_140013556
0x140013525  movzx   r9d, [rsp+68h+var_34]
0x14001352b  lea     rax, [rsp+68h+var_38]
0x140013530  mov     r8, rdi
0x140013533  mov     [rsp+68h+var_48], rax
0x140013538  mov     rdx, rsi
0x14001353b  mov     rcx, rbp
0x14001353e  call    AslEnvGetSystem32DirPathBuf
0x140013543  mov     ebx, eax
0x140013545  test    eax, eax
0x140013547  jns     short loc_14001356B
0x140013549  lea     r9, aAslenvgetsyste_0; "AslEnvGetSystem32DirPathBuf failed [%x]"
0x140013550  mov     r8d, 424h
0x140013556  lea     rdx, aSdbpgetpathsys; "SdbpGetPathSystem"
0x14001355d  mov     dword ptr [rsp+68h+var_48], eax
0x140013561  mov     ecx, 1
0x140013566  call    AslLogCallPrintf
0x14001356b  mov     eax, ebx
0x14001356d  add     rsp, 48h
0x140013571  pop     rdi
0x140013572  pop     rsi
0x140013573  pop     rbp
0x140013574  pop     rbx
0x140013575  retn
```

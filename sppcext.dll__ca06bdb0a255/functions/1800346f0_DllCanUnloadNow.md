# DllCanUnloadNow

- ea: `0x1800346f0`
- end: `0x18003472f`
- name: `DllCanUnloadNow`
- size: `63`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180043bd8`
- `0x180043eac`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // r8
  _BOOL8 v1; // rbx
  __int64 v2; // r8

  sub_180043EAC((unsigned int *)byte_180080D50, (unsigned int *)&dword_18008D7CC, v0);
  v1 = dword_18008EB30 != 0;
  sub_180043BD8((unsigned int *)byte_1800859A8, (unsigned int *)qword_18008D138, v2);
  return v1;
}

```

## disassembly

```asm
0x1800346f0  push    rbx
0x1800346f2  sub     rsp, 20h
0x1800346f6  lea     rdx, dword_18008D7CC
0x1800346fd  lea     rcx, byte_180080D50
0x180034704  call    sub_180043EAC
0x180034709  xor     ebx, ebx
0x18003470b  lea     rdx, qword_18008D138
0x180034712  cmp     cs:dword_18008EB30, ebx
0x180034718  lea     rcx, byte_1800859A8
0x18003471f  setnz   bl
0x180034722  call    sub_180043BD8
0x180034727  mov     eax, ebx
0x180034729  add     rsp, 20h
0x18003472d  pop     rbx
0x18003472e  retn
```

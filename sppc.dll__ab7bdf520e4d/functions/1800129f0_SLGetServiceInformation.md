# SLGetServiceInformation

- ea: `0x1800129f0`
- end: `0x180012a39`
- name: `SLGetServiceInformation`
- size: `73`
- prototype: `HRESULT __stdcall(HSLC hSLC, PCWSTR pwszValueName, SLDATATYPE *peDataType, UINT *pcbValue, PBYTE *ppbValue)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180002bf0`
- `0x18000c5d4`

## pseudocode

```c
HRESULT __stdcall SLGetServiceInformation(
        HSLC hSLC,
        PCWSTR pwszValueName,
        SLDATATYPE *peDataType,
        UINT *pcbValue,
        PBYTE *ppbValue)
{
  HRESULT v5; // ebx

  v5 = sub_18000C5D4(
         (_DWORD)hSLC,
         5,
         0,
         0,
         (__int64)pwszValueName,
         (__int64)peDataType,
         (__int64)pcbValue,
         (__int64)ppbValue);
  sub_180002BF0(&dword_180018D0C, &dword_18001E16C);
  return v5;
}

```

## disassembly

```asm
0x1800129f0  mov     r11, rsp
0x1800129f3  push    rbx
0x1800129f4  sub     rsp, 40h
0x1800129f8  mov     rax, [rsp+48h+ppbValue]
0x1800129fd  mov     [r11-10h], rax
0x180012a01  mov     [r11-18h], r9
0x180012a05  xor     r9d, r9d
0x180012a08  mov     [r11-20h], r8
0x180012a0c  xor     r8d, r8d
0x180012a0f  mov     [r11-28h], rdx
0x180012a13  lea     edx, [r9+5]
0x180012a17  call    sub_18000C5D4
0x180012a1c  lea     rdx, dword_18001E16C
0x180012a23  mov     ebx, eax
0x180012a25  lea     rcx, dword_180018D0C
0x180012a2c  call    sub_180002BF0
0x180012a31  mov     eax, ebx
0x180012a33  add     rsp, 40h
0x180012a37  pop     rbx
0x180012a38  retn
```

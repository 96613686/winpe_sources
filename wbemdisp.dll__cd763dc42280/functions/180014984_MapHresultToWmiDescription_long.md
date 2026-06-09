# MapHresultToWmiDescription(long)

- ea: `0x180014984`
- end: `0x180014a23`
- name: `?MapHresultToWmiDescription@@YAPEAGJ@Z`
- size: `159`
- prototype: `unsigned __int16 *__fastcall(int)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800050dc`
- `0x180014870`
- `0x180024774`
- `0x180025fa0`

## callees

- `0x180014984`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800149ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800149ba`

## pseudocode

```c
unsigned __int16 *__fastcall MapHresultToWmiDescription(unsigned int a1)
{
  LPVOID v3; // [rsp+48h] [rbp+10h] BYREF
  __int64 v4; // [rsp+50h] [rbp+18h] BYREF

  v4 = 0;
  v3 = 0;
  if ( CoCreateInstance(&CLSID_WbemStatusCodeText, 0, 1u, &IID_IWbemStatusCodeText, &v3) >= 0 )
  {
    if ( a1 == -2147209215 )
    {
      a1 = 262148;
    }
    else if ( a1 == -2147209214 )
    {
      a1 = 262146;
    }
    (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64, __int64 *))(*(_QWORD *)v3 + 24LL))(v3, a1, 0, 1, &v4);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return (unsigned __int16 *)v4;
}

```

## disassembly

```asm
0x180014984  mov     r11, rsp
0x180014987  push    rbx
0x180014988  sub     rsp, 30h
0x18001498c  xor     edx, edx; pUnkOuter
0x18001498e  mov     qword ptr [r11+18h], 0
0x180014996  mov     ebx, ecx
0x180014998  mov     qword ptr [r11+10h], 0
0x1800149a0  lea     rax, [r11+10h]
0x1800149a4  lea     r9, IID_IWbemStatusCodeText; riid
0x1800149ab  mov     [r11-18h], rax
0x1800149af  lea     r8d, [rdx+1]; dwClsContext
0x1800149b3  lea     rcx, CLSID_WbemStatusCodeText; rclsid
0x1800149ba  call    cs:__imp_CoCreateInstance
0x1800149c0  test    eax, eax
0x1800149c2  js      short loc_180014A11
0x1800149c4  cmp     ebx, 80043001h
0x1800149ca  jz      short loc_180014A1C
0x1800149cc  cmp     ebx, 80043002h
0x1800149d2  mov     eax, 40002h
0x1800149d7  cmovz   ebx, eax
0x1800149da  mov     rcx, [rsp+38h+arg_8]
0x1800149df  lea     rdx, [rsp+38h+arg_10]
0x1800149e4  mov     [rsp+38h+var_18], rdx
0x1800149e9  mov     r9d, 1
0x1800149ef  xor     r8d, r8d
0x1800149f2  mov     edx, ebx
0x1800149f4  mov     rax, [rcx]
0x1800149f7  mov     rax, [rax+18h]
0x1800149fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a00  mov     rcx, [rsp+38h+arg_8]
0x180014a05  mov     rax, [rcx]
0x180014a08  mov     rax, [rax+10h]
0x180014a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a11  mov     rax, [rsp+38h+arg_10]
0x180014a16  add     rsp, 30h
0x180014a1a  pop     rbx
0x180014a1b  retn
0x180014a1c  mov     ebx, 40004h
0x180014a21  jmp     short loc_1800149DA
```

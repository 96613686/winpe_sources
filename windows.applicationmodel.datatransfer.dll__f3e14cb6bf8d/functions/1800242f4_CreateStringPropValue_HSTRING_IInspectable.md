# CreateStringPropValue(HSTRING__ *,IInspectable * *)

- ea: `0x1800242f4`
- end: `0x1800243f6`
- name: `?CreateStringPropValue@@YAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `258`
- prototype: `__int64 __fastcall(HSTRING, struct IInspectable **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180053c10`
- `0x1800565a4`

## callees

- `0x180002ad0`
- `0x1800242f4`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002433c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002433c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024355`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024355`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002438f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002438f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateStringPropValue(HSTRING a1, struct IInspectable **a2)
{
  int ActivationFactory; // ebx
  __int64 v5; // rcx
  __int64 v7; // [rsp+20h] [rbp-38h] BYREF
  HSTRING v8; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER v9; // [rsp+30h] [rbp-28h] BYREF

  *a2 = 0;
  v7 = 0;
  if ( WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &v9, &v8) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v7);
  if ( ActivationFactory >= 0 )
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING, struct IInspectable **))(*(_QWORD *)v7 + 144LL))(
                          v7,
                          a1,
                          a2);
  v5 = v7;
  if ( v7 )
  {
    v7 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800242f4  mov     r11, rsp
0x1800242f7  mov     [r11+18h], rbx
0x1800242fb  mov     [r11+20h], rsi
0x1800242ff  push    rdi
0x180024300  sub     rsp, 50h
0x180024304  mov     rax, cs:__security_cookie
0x18002430b  xor     rax, rsp
0x18002430e  mov     [rsp+58h+var_10], rax
0x180024313  mov     rdi, rdx
0x180024316  mov     rsi, rcx
0x180024319  mov     qword ptr [rdx], 0
0x180024320  mov     qword ptr [r11-38h], 0
0x180024328  lea     r9, [r11-30h]; string
0x18002432c  lea     r8, [r11-28h]; hstringHeader
0x180024330  mov     edx, 20h ; ' '; length
0x180024335  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18002433c  call    cs:__imp_WindowsCreateStringReference
0x180024342  test    eax, eax
0x180024344  jns     short loc_18002435B
0x180024346  xor     r9d, r9d; lpArguments
0x180024349  xor     r8d, r8d; nNumberOfArguments
0x18002434c  lea     edx, [r9+1]; dwExceptionFlags
0x180024350  mov     ecx, 0C000000Dh; dwExceptionCode
0x180024355  call    cs:__imp_RaiseException
0x18002435b  mov     rbx, [rsp+58h+var_30]
0x180024360  mov     rcx, [rsp+58h+var_38]
0x180024365  test    rcx, rcx
0x180024368  jz      short loc_180024380
0x18002436a  mov     [rsp+58h+var_38], 0
0x180024373  mov     rax, [rcx]
0x180024376  mov     rax, [rax+10h]
0x18002437a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002437f  nop
0x180024380  lea     r8, [rsp+58h+var_38]
0x180024385  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18002438c  mov     rcx, rbx
0x18002438f  call    cs:__imp_RoGetActivationFactory
0x180024395  mov     ebx, eax
0x180024397  test    eax, eax
0x180024399  js      short loc_1800243B7
0x18002439b  mov     rcx, [rsp+58h+var_38]
0x1800243a0  mov     rax, [rcx]
0x1800243a3  mov     r8, rdi
0x1800243a6  mov     rdx, rsi
0x1800243a9  mov     rax, [rax+90h]
0x1800243b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243b5  mov     ebx, eax
0x1800243b7  mov     rcx, [rsp+58h+var_38]
0x1800243bc  test    rcx, rcx
0x1800243bf  jz      short loc_1800243D7
0x1800243c1  mov     [rsp+58h+var_38], 0
0x1800243ca  mov     rax, [rcx]
0x1800243cd  mov     rax, [rax+10h]
0x1800243d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243d6  nop
0x1800243d7  mov     eax, ebx
0x1800243d9  mov     rcx, [rsp+58h+var_10]
0x1800243de  xor     rcx, rsp; StackCookie
0x1800243e1  call    __security_check_cookie
0x1800243e6  mov     rbx, [rsp+58h+arg_10]
0x1800243eb  mov     rsi, [rsp+58h+arg_18]
0x1800243f0  add     rsp, 50h
0x1800243f4  pop     rdi
0x1800243f5  retn
```

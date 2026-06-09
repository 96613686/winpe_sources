# ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)

- ea: `0x18001b4c0`
- end: `0x18001b53b`
- name: `?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z`
- size: `123`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE **, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013434`
- `0x1800190bc`
- `0x180019e58`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001b4c0`
- `0x18001b9fc`

## string_xrefs

- `0x18001b4db`: `ReadStringFromRegistry`

## pseudocode

```c
__int64 __fastcall ReadStringFromRegistry(HKEY hKey, LPCWSTR lpValueName, BYTE **a3, int a4)
{
  unsigned int v8; // ebx
  int StringFromRegistry; // [rsp+30h] [rbp-68h] BYREF
  __int16 v11; // [rsp+34h] [rbp-64h]
  __int16 v12; // [rsp+36h] [rbp-62h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&StringFromRegistry, "ReadStringFromRegistry", 209, 2);
  StringFromRegistry = _ReadStringFromRegistry(hKey, lpValueName, a3, a4, 1u);
  v8 = StringFromRegistry;
  if ( StringFromRegistry >= 0 )
    v11 = 211;
  else
    v12 = 211;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&StringFromRegistry);
  return v8;
}

```

## disassembly

```asm
0x18001b4c0  push    rbx
0x18001b4c2  push    rbp
0x18001b4c3  push    rsi
0x18001b4c4  push    rdi
0x18001b4c5  sub     rsp, 78h
0x18001b4c9  mov     ebx, r9d
0x18001b4cc  mov     rdi, r8
0x18001b4cf  mov     rsi, rdx
0x18001b4d2  mov     rbp, rcx
0x18001b4d5  mov     r9d, 2; unsigned __int16
0x18001b4db  lea     rdx, aReadstringfrom; "ReadStringFromRegistry"
0x18001b4e2  mov     r8d, 0D1h; unsigned __int16
0x18001b4e8  lea     rcx, [rsp+98h+var_68]; this
0x18001b4ed  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001b4f2  mov     r9d, ebx; int
0x18001b4f5  mov     [rsp+98h+var_78], 1; unsigned int
0x18001b4fd  mov     r8, rdi; unsigned __int16 **
0x18001b500  mov     rdx, rsi; lpValueName
0x18001b503  mov     rcx, rbp; hKey
0x18001b506  call    ?_ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGHK@Z; _ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int,ulong)
0x18001b50b  mov     [rsp+98h+var_68], eax
0x18001b50f  mov     ebx, eax
0x18001b511  mov     ecx, 0D3h
0x18001b516  test    eax, eax
0x18001b518  jns     short loc_18001B521
0x18001b51a  mov     [rsp+98h+var_62], cx
0x18001b51f  jmp     short loc_18001B526
0x18001b521  mov     [rsp+98h+var_64], cx
0x18001b526  lea     rcx, [rsp+98h+var_68]; this
0x18001b52b  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001b530  mov     eax, ebx
0x18001b532  add     rsp, 78h
0x18001b536  pop     rdi
0x18001b537  pop     rsi
0x18001b538  pop     rbp
0x18001b539  pop     rbx
0x18001b53a  retn
```

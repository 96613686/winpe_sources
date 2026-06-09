# ReadExpandStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)

- ea: `0x18001b438`
- end: `0x18001b4ba`
- name: `?ReadExpandStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z`
- size: `130`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, BYTE **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180019ca0`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001b438`
- `0x18001b9fc`

## string_xrefs

- `0x18001b476`: `ProfileImagePath`
- `0x18001b445`: `ReadExpandStringFromRegistry`

## pseudocode

```c
__int64 __fastcall ReadExpandStringFromRegistry(HKEY hKey, const unsigned __int16 *a2, BYTE **a3)
{
  unsigned int v5; // ebx
  int StringFromRegistry; // [rsp+30h] [rbp-48h] BYREF
  __int16 v8; // [rsp+34h] [rbp-44h]
  __int16 v9; // [rsp+36h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&StringFromRegistry, "ReadExpandStringFromRegistry", 226, 2);
  StringFromRegistry = _ReadStringFromRegistry(hKey, L"ProfileImagePath", a3, 1, 2u);
  v5 = StringFromRegistry;
  if ( StringFromRegistry >= 0 )
    v8 = 228;
  else
    v9 = 228;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&StringFromRegistry);
  return v5;
}

```

## disassembly

```asm
0x18001b438  mov     [rsp+arg_0], rbx
0x18001b43d  push    rdi
0x18001b43e  sub     rsp, 70h
0x18001b442  mov     rbx, r8
0x18001b445  lea     rdx, aReadexpandstri; "ReadExpandStringFromRegistry"
0x18001b44c  mov     rdi, rcx
0x18001b44f  mov     r8d, 0E2h; unsigned __int16
0x18001b455  lea     rcx, [rsp+78h+var_48]; this
0x18001b45a  mov     r9d, 2; unsigned __int16
0x18001b460  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001b465  mov     r9d, 1; int
0x18001b46b  mov     [rsp+78h+var_58], 2; unsigned int
0x18001b473  mov     r8, rbx; unsigned __int16 **
0x18001b476  lea     rdx, c_wszProfileImagePath; "ProfileImagePath"
0x18001b47d  mov     rcx, rdi; hKey
0x18001b480  call    ?_ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGHK@Z; _ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int,ulong)
0x18001b485  mov     [rsp+78h+var_48], eax
0x18001b489  mov     ebx, eax
0x18001b48b  mov     ecx, 0E4h
0x18001b490  test    eax, eax
0x18001b492  jns     short loc_18001B49B
0x18001b494  mov     [rsp+78h+var_42], cx
0x18001b499  jmp     short loc_18001B4A0
0x18001b49b  mov     [rsp+78h+var_44], cx
0x18001b4a0  lea     rcx, [rsp+78h+var_48]; this
0x18001b4a5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001b4aa  mov     eax, ebx
0x18001b4ac  mov     rbx, [rsp+78h+arg_0]
0x18001b4b4  add     rsp, 70h
0x18001b4b8  pop     rdi
0x18001b4b9  retn
```

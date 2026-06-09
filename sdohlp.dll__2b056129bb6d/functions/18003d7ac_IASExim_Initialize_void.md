# IASExim::Initialize(void)

- ea: `0x18003d7ac`
- end: `0x18003d8ae`
- name: `?Initialize@IASExim@@QEAAJXZ`
- size: `258`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002d770`

## callees

- `0x18002cd00`
- `0x18003d7ac`
- `0x180042a80`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003d7d6`
- `ole32!CoCreateInstance` at `0x18003d83e`
- `ole32!CoCreateInstance` at `0x18003d7d6`
- `ole32!CoCreateInstance` at `0x18003d83e`

## string_xrefs

- `0x18003d812`: `CoCi(CIASNetshXMLHelper) failed with 0x%x`
- `0x18003d86e`: `CoCi(CIASNetshXMLHelper) failed with 0x%x`

## pseudocode

```c
__int64 __fastcall IASExim::Initialize(LPVOID *ppv)
{
  HRESULT Instance; // ebx
  int v3; // edx

  Instance = CoCreateInstance(
               &GUID_88d96a05_f192_11d4_a65f_0040963251e5,
               0,
               3u,
               &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60,
               ppv + 1);
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(
                 &GUID_227ec397_6791_4ac6_a762_2f70f99015c2,
                 0,
                 3u,
                 &GUID_8153e30d_efc4_4dcb_9db7_2114125d6c50,
                 ppv);
    if ( Instance < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("CoCi(CIASNetshXMLHelper) failed with 0x%x");
      v3 = 24;
      goto LABEL_11;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("CoCi(CIASNetshXMLHelper) failed with 0x%x");
    v3 = 23;
LABEL_11:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      (unsigned int)&WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids,
      (unsigned int)"NPSSDO",
      Instance);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003d7ac  mov     [rsp+arg_0], rbx
0x18003d7b1  push    rdi
0x18003d7b2  sub     rsp, 30h
0x18003d7b6  lea     rax, [rcx+8]
0x18003d7ba  xor     edx, edx; pUnkOuter
0x18003d7bc  mov     rdi, rcx
0x18003d7bf  mov     [rsp+38h+ppv], rax; ppv
0x18003d7c4  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x18003d7cb  lea     rcx, _GUID_88d96a05_f192_11d4_a65f_0040963251e5; rclsid
0x18003d7d2  lea     r8d, [rdx+3]; dwClsContext
0x18003d7d6  call    cs:__imp_CoCreateInstance
0x18003d7dc  mov     ebx, eax
0x18003d7de  test    eax, eax
0x18003d7e0  jns     short loc_18003D825
0x18003d7e2  mov     rax, cs:WPP_GLOBAL_Control
0x18003d7e9  lea     rcx, WPP_GLOBAL_Control
0x18003d7f0  cmp     rax, rcx
0x18003d7f3  jz      loc_18003D8A1
0x18003d7f9  cmp     byte ptr [rax+19h], 2
0x18003d7fd  jb      loc_18003D8A1
0x18003d803  test    dword ptr [rax+1Ch], 400h
0x18003d80a  jz      loc_18003D8A1
0x18003d810  mov     edx, ebx
0x18003d812  lea     rcx, aCociCiasnetshx; "CoCi(CIASNetshXMLHelper) failed with 0x"...
0x18003d819  call    WppDbgPrint
0x18003d81e  mov     edx, 17h
0x18003d823  jmp     short loc_18003D87F
0x18003d825  xor     edx, edx; pUnkOuter
0x18003d827  mov     [rsp+38h+ppv], rdi; ppv
0x18003d82c  lea     r9, _GUID_8153e30d_efc4_4dcb_9db7_2114125d6c50; riid
0x18003d833  lea     rcx, _GUID_227ec397_6791_4ac6_a762_2f70f99015c2; rclsid
0x18003d83a  lea     r8d, [rdx+3]; dwClsContext
0x18003d83e  call    cs:__imp_CoCreateInstance
0x18003d844  mov     ebx, eax
0x18003d846  test    eax, eax
0x18003d848  jns     short loc_18003D8A1
0x18003d84a  mov     rax, cs:WPP_GLOBAL_Control
0x18003d851  lea     rcx, WPP_GLOBAL_Control
0x18003d858  cmp     rax, rcx
0x18003d85b  jz      short loc_18003D8A1
0x18003d85d  cmp     byte ptr [rax+19h], 2
0x18003d861  jb      short loc_18003D8A1
0x18003d863  test    dword ptr [rax+1Ch], 400h
0x18003d86a  jz      short loc_18003D8A1
0x18003d86c  mov     edx, ebx
0x18003d86e  lea     rcx, aCociCiasnetshx; "CoCi(CIASNetshXMLHelper) failed with 0x"...
0x18003d875  call    WppDbgPrint
0x18003d87a  mov     edx, 18h
0x18003d87f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d886  lea     r9, aNpssdo; "NPSSDO"
0x18003d88d  lea     r8, WPP_db6699a6e9cd39d84f3e50670283d06f_Traceguids
0x18003d894  mov     dword ptr [rsp+38h+ppv], ebx
0x18003d898  mov     rcx, [rcx+10h]
0x18003d89c  call    WPP_SF_sd
0x18003d8a1  mov     eax, ebx
0x18003d8a3  mov     rbx, [rsp+38h+arg_0]
0x18003d8a8  add     rsp, 30h
0x18003d8ac  pop     rdi
0x18003d8ad  retn
```

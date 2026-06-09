# CProvideWinSATVisuals::GetHighContrastState(int &)

- ea: `0x18001e3a8`
- end: `0x18001e3f5`
- name: `?GetHighContrastState@CProvideWinSATVisuals@@CAJAEAH@Z`
- size: `77`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800119a4`

## callees

- `0x18001e3a8`

## import_xrefs

- `USER32!SystemParametersInfoW` at `0x18001e3cd`
- `USER32!SystemParametersInfoW` at `0x18001e3cd`

## pseudocode

```c
__int64 __fastcall CProvideWinSATVisuals::GetHighContrastState(int *a1)
{
  BOOL v2; // eax
  int v3; // ecx
  __int128 pvParam; // [rsp+20h] [rbp-18h] BYREF

  pvParam = 0;
  LODWORD(pvParam) = 16;
  v2 = SystemParametersInfoW(0x42u, 0x10u, &pvParam, 0);
  if ( v2 )
    v3 = BYTE4(pvParam) & 1;
  else
    v3 = 0;
  *a1 = v3;
  return !v2 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x18001e3a8  push    rbx
0x18001e3aa  sub     rsp, 30h
0x18001e3ae  mov     edx, 10h; uiParam
0x18001e3b3  lea     r8, [rsp+38h+pvParam]; pvParam
0x18001e3b8  xorps   xmm0, xmm0
0x18001e3bb  mov     rbx, rcx
0x18001e3be  movups  [rsp+38h+pvParam], xmm0
0x18001e3c3  xor     r9d, r9d; fWinIni
0x18001e3c6  mov     dword ptr [rsp+38h+pvParam], edx
0x18001e3ca  lea     ecx, [rdx+32h]; uiAction
0x18001e3cd  call    cs:__imp_SystemParametersInfoW
0x18001e3d3  test    eax, eax
0x18001e3d5  jz      short loc_18001E3E0
0x18001e3d7  mov     ecx, dword ptr [rsp+38h+pvParam+4]
0x18001e3db  and     ecx, 1
0x18001e3de  jmp     short loc_18001E3E2
0x18001e3e0  xor     ecx, ecx
0x18001e3e2  neg     eax
0x18001e3e4  mov     [rbx], ecx
0x18001e3e6  sbb     eax, eax
0x18001e3e8  not     eax
0x18001e3ea  and     eax, 80004005h
0x18001e3ef  add     rsp, 30h
0x18001e3f3  pop     rbx
0x18001e3f4  retn
```

# Settings::get_PackagePath(ushort * *)

- ea: `0x18001e808`
- end: `0x18001e8a7`
- name: `?get_PackagePath@Settings@@QEAAJPEAPEAG@Z`
- size: `159`
- prototype: `__int64 __fastcall(Settings *__hidden this, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000615c`
- `0x18000bef0`
- `0x18000fc10`
- `0x18001dc28`

## callees

- `0x1800012a4`
- `0x18001e808`
- `0x180026fa0`
- `0x180027aa0`

## string_xrefs

- `0x18001e82f`: `Settings::get_PackagePath`
- `0x18001e86c`: `Settings::get_PackagePath`

## pseudocode

```c
__int64 __fastcall Settings::get_PackagePath(Settings *this, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  int v4; // r8d
  const unsigned __int16 *v5; // rdx
  int v6; // eax
  unsigned __int16 *v7; // rcx
  unsigned __int16 *v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    v4 = 89;
LABEL_3:
    SdpDebugTrace(1u, L"Settings::get_PackagePath", v4, v3);
    return v3;
  }
  v5 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  if ( !v5 )
  {
    v3 = -2147467261;
    v4 = 97;
    goto LABEL_3;
  }
  v6 = SdpStrCpy(&v9, v5);
  v3 = v6;
  if ( v6 >= 0 )
  {
    v7 = 0;
    *a2 = v9;
  }
  else
  {
    SdpDebugTrace(1u, L"Settings::get_PackagePath", 99, v6);
    v7 = v9;
  }
  if ( v7 )
    operator delete(v7);
  return v3;
}

```

## disassembly

```asm
0x18001e808  mov     [rsp+arg_0], rbx
0x18001e80d  push    rdi
0x18001e80e  sub     rsp, 20h
0x18001e812  mov     [rsp+28h+arg_8], 0
0x18001e81b  mov     rdi, rdx
0x18001e81e  test    rdx, rdx
0x18001e821  jnz     short loc_18001E842
0x18001e823  mov     ebx, 80070057h
0x18001e828  lea     r8d, [rdx+59h]; int
0x18001e82c  mov     r9d, ebx; int
0x18001e82f  lea     rdx, aSettingsGetPac; "Settings::get_PackagePath"
0x18001e836  mov     ecx, 1; Level
0x18001e83b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e840  jmp     short loc_18001E89A
0x18001e842  mov     rdx, [rcx+8]; unsigned __int16 *
0x18001e846  test    rdx, rdx
0x18001e849  jnz     short loc_18001E856
0x18001e84b  mov     ebx, 80004003h
0x18001e850  lea     r8d, [rdx+61h]
0x18001e854  jmp     short loc_18001E82C
0x18001e856  lea     rcx, [rsp+28h+arg_8]; unsigned __int16 **
0x18001e85b  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x18001e860  mov     ebx, eax
0x18001e862  test    eax, eax
0x18001e864  jns     short loc_18001E886
0x18001e866  mov     r8d, 63h ; 'c'; int
0x18001e86c  lea     rdx, aSettingsGetPac; "Settings::get_PackagePath"
0x18001e873  mov     r9d, eax; int
0x18001e876  lea     ecx, [r8-62h]; Level
0x18001e87a  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e87f  mov     rcx, [rsp+28h+arg_8]
0x18001e884  jmp     short loc_18001E890
0x18001e886  mov     rax, [rsp+28h+arg_8]
0x18001e88b  xor     ecx, ecx; Block
0x18001e88d  mov     [rdi], rax
0x18001e890  test    rcx, rcx
0x18001e893  jz      short loc_18001E89A
0x18001e895  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e89a  mov     eax, ebx
0x18001e89c  mov     rbx, [rsp+28h+arg_0]
0x18001e8a1  add     rsp, 20h
0x18001e8a5  pop     rdi
0x18001e8a6  retn
```

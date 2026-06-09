# Settings::get_ResultPath(ushort * *)

- ea: `0x18001e95c`
- end: `0x18001ea00`
- name: `?get_ResultPath@Settings@@QEAAJPEAPEAG@Z`
- size: `164`
- prototype: `__int64 __fastcall(Settings *__hidden this, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1800034c4`
- `0x18000d63c`
- `0x1800100b0`
- `0x180021914`

## callees

- `0x1800012a4`
- `0x18001e95c`
- `0x180026fa0`
- `0x180027aa0`

## string_xrefs

- `0x18001e985`: `Settings::get_ResultPath`
- `0x18001e9c1`: `Settings::get_ResultPath`

## pseudocode

```c
__int64 __fastcall Settings::get_ResultPath(Settings *this, unsigned __int16 **a2)
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
    v4 = 278;
LABEL_3:
    SdpDebugTrace(1u, L"Settings::get_ResultPath", v4, v3);
    return v3;
  }
  v5 = (const unsigned __int16 *)*((_QWORD *)this + 3);
  if ( !v5 )
  {
    v3 = -2147467261;
    v4 = 280;
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
    SdpDebugTrace(1u, L"Settings::get_ResultPath", 282, v6);
    v7 = v9;
  }
  if ( v7 )
    operator delete(v7);
  return v3;
}

```

## disassembly

```asm
0x18001e95c  mov     [rsp+arg_0], rbx
0x18001e961  push    rdi
0x18001e962  sub     rsp, 20h
0x18001e966  mov     [rsp+28h+arg_8], 0
0x18001e96f  mov     rdi, rdx
0x18001e972  test    rdx, rdx
0x18001e975  jnz     short loc_18001E998
0x18001e977  mov     ebx, 80070057h
0x18001e97c  mov     r8d, 116h; int
0x18001e982  mov     r9d, ebx; int
0x18001e985  lea     rdx, aSettingsGetRes; "Settings::get_ResultPath"
0x18001e98c  mov     ecx, 1; Level
0x18001e991  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e996  jmp     short loc_18001E9F3
0x18001e998  mov     rdx, [rcx+18h]; unsigned __int16 *
0x18001e99c  test    rdx, rdx
0x18001e99f  jnz     short loc_18001E9AE
0x18001e9a1  mov     ebx, 80004003h
0x18001e9a6  mov     r8d, 118h
0x18001e9ac  jmp     short loc_18001E982
0x18001e9ae  lea     rcx, [rsp+28h+arg_8]; unsigned __int16 **
0x18001e9b3  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x18001e9b8  mov     ebx, eax
0x18001e9ba  test    eax, eax
0x18001e9bc  jns     short loc_18001E9DF
0x18001e9be  mov     r9d, eax; int
0x18001e9c1  lea     rdx, aSettingsGetRes; "Settings::get_ResultPath"
0x18001e9c8  mov     r8d, 11Ah; int
0x18001e9ce  mov     ecx, 1; Level
0x18001e9d3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e9d8  mov     rcx, [rsp+28h+arg_8]
0x18001e9dd  jmp     short loc_18001E9E9
0x18001e9df  mov     rax, [rsp+28h+arg_8]
0x18001e9e4  xor     ecx, ecx; Block
0x18001e9e6  mov     [rdi], rax
0x18001e9e9  test    rcx, rcx
0x18001e9ec  jz      short loc_18001E9F3
0x18001e9ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e9f3  mov     eax, ebx
0x18001e9f5  mov     rbx, [rsp+28h+arg_0]
0x18001e9fa  add     rsp, 20h
0x18001e9fe  pop     rdi
0x18001e9ff  retn
```

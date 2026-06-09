# Settings::get_Locale(ushort * *)

- ea: `0x18001e6c0`
- end: `0x18001e755`
- name: `?get_Locale@Settings@@QEAAJPEAPEAG@Z`
- size: `149`
- prototype: `__int64 __fastcall(Settings *__hidden this, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000a86c`
- `0x18000d63c`
- `0x180011ba4`
- `0x180016630`
- `0x18002114c`

## callees

- `0x1800012a4`
- `0x18001e6c0`
- `0x180026fa0`
- `0x180027aa0`

## pseudocode

```c
__int64 __fastcall Settings::get_Locale(Settings *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rax
  unsigned int v4; // ebx
  const unsigned __int16 *v5; // rdx
  int v6; // eax
  unsigned __int16 *v7; // rcx
  unsigned __int16 *v9; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v9 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    SdpDebugTrace(1u, L"Settings::get_Locale", 667, -2147024809);
    return v4;
  }
  v5 = (const unsigned __int16 *)*((_QWORD *)this + 8);
  v4 = 0;
  if ( v5 )
  {
    v6 = SdpStrCpy(&v9, v5);
    v4 = v6;
    if ( v6 < 0 )
    {
      SdpDebugTrace(1u, L"Settings::get_Locale", 671, v6);
      v7 = v9;
      goto LABEL_8;
    }
    v2 = v9;
  }
  *a2 = v2;
  v7 = 0;
LABEL_8:
  if ( v7 )
    operator delete(v7);
  return v4;
}

```

## disassembly

```asm
0x18001e6c0  mov     [rsp+arg_0], rbx
0x18001e6c5  push    rdi
0x18001e6c6  sub     rsp, 20h
0x18001e6ca  xor     eax, eax
0x18001e6cc  mov     rdi, rdx
0x18001e6cf  mov     [rsp+28h+arg_8], rax
0x18001e6d4  test    rdx, rdx
0x18001e6d7  jnz     short loc_18001E6F8
0x18001e6d9  mov     ebx, 80070057h
0x18001e6de  lea     rdx, aSettingsGetLoc; "Settings::get_Locale"
0x18001e6e5  mov     r9d, ebx; int
0x18001e6e8  lea     ecx, [rdi+1]; Level
0x18001e6eb  mov     r8d, 29Bh; int
0x18001e6f1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e6f6  jmp     short loc_18001E748
0x18001e6f8  mov     rdx, [rcx+40h]; unsigned __int16 *
0x18001e6fc  xor     ebx, ebx
0x18001e6fe  test    rdx, rdx
0x18001e701  jz      short loc_18001E739
0x18001e703  lea     rcx, [rsp+28h+arg_8]; unsigned __int16 **
0x18001e708  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x18001e70d  mov     ebx, eax
0x18001e70f  test    eax, eax
0x18001e711  jns     short loc_18001E734
0x18001e713  mov     r9d, eax; int
0x18001e716  lea     rdx, aSettingsGetLoc; "Settings::get_Locale"
0x18001e71d  mov     r8d, 29Fh; int
0x18001e723  mov     ecx, 1; Level
0x18001e728  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e72d  mov     rcx, [rsp+28h+arg_8]
0x18001e732  jmp     short loc_18001E73E
0x18001e734  mov     rax, [rsp+28h+arg_8]
0x18001e739  mov     [rdi], rax
0x18001e73c  xor     ecx, ecx; Block
0x18001e73e  test    rcx, rcx
0x18001e741  jz      short loc_18001E748
0x18001e743  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e748  mov     eax, ebx
0x18001e74a  mov     rbx, [rsp+28h+arg_0]
0x18001e74f  add     rsp, 20h
0x18001e753  pop     rdi
0x18001e754  retn
```

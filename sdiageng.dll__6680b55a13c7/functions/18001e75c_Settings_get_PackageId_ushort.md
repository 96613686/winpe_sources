# Settings::get_PackageId(ushort * *)

- ea: `0x18001e75c`
- end: `0x18001e800`
- name: `?get_PackageId@Settings@@QEAAJPEAPEAG@Z`
- size: `164`
- prototype: `__int64 __fastcall(Settings *__hidden this, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000ad80`
- `0x18000cf00`
- `0x18000fcf0`
- `0x180011630`
- `0x1800151fc`
- `0x180016630`
- `0x18001b0b4`

## callees

- `0x1800012a4`
- `0x18001e75c`
- `0x180026fa0`
- `0x180027aa0`

## pseudocode

```c
__int64 __fastcall Settings::get_PackageId(Settings *this, unsigned __int16 **a2)
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
    v4 = 184;
LABEL_3:
    SdpDebugTrace(1u, L"Settings::get_PackageId", v4, v3);
    return v3;
  }
  v5 = (const unsigned __int16 *)*((_QWORD *)this + 2);
  if ( !v5 )
  {
    v3 = -2147467261;
    v4 = 191;
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
    SdpDebugTrace(1u, L"Settings::get_PackageId", 193, v6);
    v7 = v9;
  }
  if ( v7 )
    operator delete(v7);
  return v3;
}

```

## disassembly

```asm
0x18001e75c  mov     [rsp+arg_0], rbx
0x18001e761  push    rdi
0x18001e762  sub     rsp, 20h
0x18001e766  mov     [rsp+28h+arg_8], 0
0x18001e76f  mov     rdi, rdx
0x18001e772  test    rdx, rdx
0x18001e775  jnz     short loc_18001E798
0x18001e777  mov     ebx, 80070057h
0x18001e77c  mov     r8d, 0B8h; int
0x18001e782  mov     r9d, ebx; int
0x18001e785  lea     rdx, aSettingsGetPac_2; "Settings::get_PackageId"
0x18001e78c  mov     ecx, 1; Level
0x18001e791  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e796  jmp     short loc_18001E7F3
0x18001e798  mov     rdx, [rcx+10h]; unsigned __int16 *
0x18001e79c  test    rdx, rdx
0x18001e79f  jnz     short loc_18001E7AE
0x18001e7a1  mov     ebx, 80004003h
0x18001e7a6  mov     r8d, 0BFh
0x18001e7ac  jmp     short loc_18001E782
0x18001e7ae  lea     rcx, [rsp+28h+arg_8]; unsigned __int16 **
0x18001e7b3  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x18001e7b8  mov     ebx, eax
0x18001e7ba  test    eax, eax
0x18001e7bc  jns     short loc_18001E7DF
0x18001e7be  mov     r9d, eax; int
0x18001e7c1  lea     rdx, aSettingsGetPac_2; "Settings::get_PackageId"
0x18001e7c8  mov     r8d, 0C1h; int
0x18001e7ce  mov     ecx, 1; Level
0x18001e7d3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001e7d8  mov     rcx, [rsp+28h+arg_8]
0x18001e7dd  jmp     short loc_18001E7E9
0x18001e7df  mov     rax, [rsp+28h+arg_8]
0x18001e7e4  xor     ecx, ecx; Block
0x18001e7e6  mov     [rdi], rax
0x18001e7e9  test    rcx, rcx
0x18001e7ec  jz      short loc_18001E7F3
0x18001e7ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e7f3  mov     eax, ebx
0x18001e7f5  mov     rbx, [rsp+28h+arg_0]
0x18001e7fa  add     rsp, 20h
0x18001e7fe  pop     rdi
0x18001e7ff  retn
```

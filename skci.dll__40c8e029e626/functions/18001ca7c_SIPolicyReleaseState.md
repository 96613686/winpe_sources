# SIPolicyReleaseState

- ea: `0x18001ca7c`
- end: `0x18001caf0`
- name: `SIPolicyReleaseState`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011090`
- `0x180013130`
- `0x180019cd0`
- `0x18001c380`
- `0x18001c6d4`
- `0x180048344`
- `0x1800492f8`
- `0x180049860`
- `0x18004ab74`

## callees

- `0x1800187d4`
- `0x18001c9ac`
- `0x18001ca7c`

## pseudocode

```c
void __fastcall SIPolicyReleaseState(__int64 *a1)
{
  __int64 v1; // rbx
  signed __int64 v2; // rax
  bool v3; // cc
  signed __int64 v4; // rax

  v1 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    v2 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v1 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v3 = v2 <= 1;
    v4 = v2 - 1;
    if ( v3 )
    {
      if ( v4 )
        __fastfail(0xEu);
      SIPolicyReleaseMutableState(v1);
      *(_QWORD *)v1 = 0;
      *(_QWORD *)(v1 + 24) = v1 + 16;
      *(_QWORD *)(v1 + 16) = v1 + 16;
      SIPolicyFree(*(_QWORD *)(v1 + 40));
      *(_DWORD *)(v1 + 36) = 0;
      *(_QWORD *)(v1 + 40) = 0;
      SIPolicyFree(v1);
    }
  }
}

```

## disassembly

```asm
0x18001ca7c  push    rbx
0x18001ca7e  sub     rsp, 20h
0x18001ca82  mov     rbx, [rcx]
0x18001ca85  test    rbx, rbx
0x18001ca88  jz      short loc_18001CAE9
0x18001ca8a  mov     qword ptr [rcx], 0
0x18001ca91  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ca95  lock xadd [rbx+8], rax
0x18001ca9b  sub     rax, 1
0x18001ca9f  jg      short loc_18001CAE9
0x18001caa1  test    rax, rax
0x18001caa4  jz      short loc_18001CAAF
0x18001caa6  mov     ecx, 0Eh
0x18001caab  int     29h; Win8: RtlFailFast(ecx)
0x18001caad  jmp     short loc_18001CAE9
0x18001caaf  mov     rcx, rbx
0x18001cab2  call    SIPolicyReleaseMutableState
0x18001cab7  lea     rax, [rbx+10h]
0x18001cabb  mov     qword ptr [rbx], 0
0x18001cac2  mov     [rax+8], rax
0x18001cac6  mov     [rax], rax
0x18001cac9  mov     rcx, [rbx+28h]
0x18001cacd  call    SIPolicyFree
0x18001cad2  mov     rcx, rbx
0x18001cad5  mov     dword ptr [rbx+24h], 0
0x18001cadc  mov     qword ptr [rbx+28h], 0
0x18001cae4  call    SIPolicyFree
0x18001cae9  add     rsp, 20h
0x18001caed  pop     rbx
0x18001caee  retn
```

# SkiUpdateXStateForKernelTrap

- ea: `0x140093ed0`
- end: `0x140093f8a`
- name: `SkiUpdateXStateForKernelTrap`
- size: `186`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `17`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1400eef20`
- `0x1400f0850`
- `0x1400f0b40`
- `0x1400f0f70`
- `0x1400f1420`
- `0x1400f1a50`
- `0x1400f1f30`
- `0x1400f2410`
- `0x1400f28f0`
- `0x1400f30c0`
- `0x1400f3c20`
- `0x1400f48c0`
- `0x1400f5440`
- `0x1400f6b00`
- `0x1400f89c0`
- `0x1400f9040`
- `0x1400f9340`

## callees

- `0x1400119c4`
- `0x140093ed0`
- `0x14009419c`
- `0x1400d6d4c`

## pseudocode

```c
unsigned __int64 __fastcall SkiUpdateXStateForKernelTrap(ULONG_PTR BugCheckParameter3, char a2)
{
  unsigned __int64 result; // rax
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // r10
  unsigned __int64 v5; // r11
  __int64 v6; // r10

  result = __readcr4();
  if ( (result & 0x40000) != 0 )
  {
    ExceptionList = KeGetPcr()->NtTib.ExceptionList;
    result = *(unsigned int *)(BugCheckParameter3 + 328);
    if ( (result & 2) != 0 )
      SkeBugCheckEx(0x131u, 0xBu, (ULONG_PTR)ExceptionList, BugCheckParameter3, 0);
    if ( a2 )
    {
      result = HIDWORD(ExceptionList[12].Handler);
      if ( (result & 2) == 0 )
      {
        v5 = SkeEnabledXStateFeatures & 0xFFFFFFFFFFFFFFFCuLL;
        if ( (result & 4) == 0 )
        {
          SkiXSaveS(ExceptionList[157].Handler, SkeEnabledXStateFeatures & 0xFFFFFFFFFFFFFFFCuLL);
          *(_DWORD *)(v6 + 204) |= 4u;
        }
        _RCX = *(_QWORD *)(BugCheckParameter3 + 320);
        if ( (MEMORY[0xFFFFF780000003EC] & 2) != 0 )
        {
          result = v5 & *(_QWORD *)(_RCX + 520);
          __asm { xrstors byte ptr [rcx] }
        }
        else
        {
          return RtlXRestore(_RCX, v5);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140093ed0  push    rbx
0x140093ed2  sub     rsp, 30h
0x140093ed6  mov     rbx, rcx
0x140093ed9  mov     rax, cr4
0x140093edc  bt      rax, 12h
0x140093ee1  jnb     loc_140093F83
0x140093ee7  mov     r10, gs:0
0x140093ef0  mov     eax, [rcx+148h]
0x140093ef6  test    al, 2
0x140093ef8  jz      short loc_140093F19
0x140093efa  mov     r9, rcx; BugCheckParameter3
0x140093efd  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x140093f06  mov     ecx, 131h; BugCheckCode
0x140093f0b  mov     r8, r10; BugCheckParameter2
0x140093f0e  mov     edx, 0Bh; BugCheckParameter1
0x140093f13  call    SkeBugCheckEx
0x140093f19  test    dl, dl
0x140093f1b  jz      short loc_140093F83
0x140093f1d  mov     eax, [r10+0CCh]
0x140093f24  test    al, 2
0x140093f26  jnz     short loc_140093F83
0x140093f28  mov     r11, cs:SkeEnabledXStateFeatures
0x140093f2f  and     r11, 0FFFFFFFFFFFFFFFCh
0x140093f33  test    al, 4
0x140093f35  jnz     short loc_140093F4E
0x140093f37  mov     rcx, [r10+9D8h]
0x140093f3e  mov     rdx, r11
0x140093f41  call    SkiXSaveS
0x140093f46  or      dword ptr [r10+0CCh], 4
0x140093f4e  mov     rcx, [rbx+140h]
0x140093f55  mov     rax, 0FFFFF780000003ECh
0x140093f5f  mov     eax, [rax]
0x140093f61  test    al, 2
0x140093f63  jnz     short loc_140093F6F
0x140093f65  mov     rdx, r11
0x140093f68  call    RtlXRestore
0x140093f6d  jmp     short loc_140093F83
0x140093f6f  mov     rdx, [rcx+208h]
0x140093f76  and     rdx, r11
0x140093f79  mov     rax, rdx
0x140093f7c  shr     rdx, 20h
0x140093f80  xrstors byte ptr [rcx]
0x140093f83  add     rsp, 30h
0x140093f87  pop     rbx
0x140093f88  retn
```

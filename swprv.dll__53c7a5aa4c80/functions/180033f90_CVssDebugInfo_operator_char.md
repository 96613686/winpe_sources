# CVssDebugInfo::operator<<(char *)

- ea: `0x180033f90`
- end: `0x180034032`
- name: `??6CVssDebugInfo@@QEAA?AU0@PEAD@Z`
- size: `162`
- prototype: `CVssDebugInfo *__fastcall(struct CVssDebugInfo *, CVssDebugInfo *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040cb0`

## callees

- `0x1800339c0`
- `0x180033f90`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180033ffb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180033ffb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033fc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033fc6`

## pseudocode

```c
CVssDebugInfo *__fastcall CVssDebugInfo::operator<<(struct CVssDebugInfo *a1, CVssDebugInfo *this)
{
  WCHAR *lpWideCharStr; // rax
  WCHAR *v5; // rsi

  if ( !*((_BYTE *)a1 + 162) && *((_BYTE *)a1 + 163) && *((_WORD *)a1 + 80) < 0xFu )
  {
    lpWideCharStr = (WCHAR *)CoTaskMemAlloc(0x5Cu);
    v5 = lpWideCharStr;
    if ( lpWideCharStr )
    {
      MultiByteToWideChar(0, 8u, "while calling GetStorageDependencyInformation", -1, lpWideCharStr, 46);
      *((_QWORD *)a1 + (unsigned __int16)(*((_WORD *)a1 + 80))++ + 5) = v5;
    }
    else
    {
      *((_BYTE *)a1 + 162) = 1;
    }
  }
  CVssDebugInfo::CVssDebugInfo(this, a1);
  return this;
}

```

## disassembly

```asm
0x180033f90  mov     [rsp+arg_0], rbx
0x180033f95  mov     [rsp+arg_8], rsi
0x180033f9a  push    rdi
0x180033f9b  sub     rsp, 30h
0x180033f9f  cmp     byte ptr [rcx+0A2h], 0
0x180033fa6  mov     rdi, rdx
0x180033fa9  mov     rbx, rcx
0x180033fac  jnz     short loc_180034014
0x180033fae  cmp     byte ptr [rcx+0A3h], 0
0x180033fb5  jz      short loc_180034014
0x180033fb7  cmp     word ptr [rcx+0A0h], 0Fh
0x180033fbf  jnb     short loc_180034014
0x180033fc1  mov     ecx, 5Ch ; '\'; cb
0x180033fc6  call    cs:__imp_CoTaskMemAlloc
0x180033fcc  mov     rsi, rax
0x180033fcf  test    rax, rax
0x180033fd2  jnz     short loc_180033FDD
0x180033fd4  mov     byte ptr [rbx+0A2h], 1
0x180033fdb  jmp     short loc_180034014
0x180033fdd  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180033fe1  mov     [rsp+38h+cchWideChar], 2Eh ; '.'; cchWideChar
0x180033fe9  lea     r8, MultiByteStr; "while calling GetStorageDependencyInfor"...
0x180033ff0  mov     [rsp+38h+lpWideCharStr], rsi; lpWideCharStr
0x180033ff5  xor     ecx, ecx; CodePage
0x180033ff7  lea     edx, [r9+9]; dwFlags
0x180033ffb  call    cs:__imp_MultiByteToWideChar
0x180034001  movzx   eax, word ptr [rbx+0A0h]
0x180034008  mov     [rbx+rax*8+28h], rsi
0x18003400d  inc     word ptr [rbx+0A0h]
0x180034014  mov     rdx, rbx; struct CVssDebugInfo *
0x180034017  mov     rcx, rdi; this
0x18003401a  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x18003401f  mov     rbx, [rsp+38h+arg_0]
0x180034024  mov     rax, rdi
0x180034027  mov     rsi, [rsp+38h+arg_8]
0x18003402c  add     rsp, 30h
0x180034030  pop     rdi
0x180034031  retn
```

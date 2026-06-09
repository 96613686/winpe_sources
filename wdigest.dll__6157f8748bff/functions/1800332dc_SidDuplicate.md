# SidDuplicate

- ea: `0x1800332dc`
- end: `0x180033362`
- name: `SidDuplicate`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180026ad0`

## callees

- `0x1800061a0`
- `0x180011fec`
- `0x1800332dc`
- `0x1800377bc`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800332f4`
- `ntdll!RtlLengthSid` at `0x1800332f4`

## pseudocode

```c
__int64 __fastcall SidDuplicate(_QWORD *a1, void *a2)
{
  ULONG v4; // esi
  void *Memory; // rax
  unsigned int v6; // ebx

  v4 = RtlLengthSid(a2);
  Memory = (void *)DigestAllocateMemory(v4);
  *a1 = Memory;
  if ( Memory )
  {
    v6 = 0;
    memcpy_0(Memory, a2, v4);
  }
  else
  {
    v6 = -1073741670;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_5a1eec0057703498b5d13460810c8614_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x1800332dc  mov     [rsp+arg_0], rbx
0x1800332e1  mov     [rsp+arg_8], rsi
0x1800332e6  push    rdi
0x1800332e7  sub     rsp, 20h
0x1800332eb  mov     rbx, rcx
0x1800332ee  mov     rdi, rdx
0x1800332f1  mov     rcx, rdx; Sid
0x1800332f4  call    cs:__imp_RtlLengthSid
0x1800332fa  mov     ecx, eax; Size
0x1800332fc  mov     esi, eax
0x1800332fe  call    DigestAllocateMemory
0x180033303  mov     [rbx], rax
0x180033306  test    rax, rax
0x180033309  jz      short loc_18003331D
0x18003330b  xor     ebx, ebx
0x18003330d  mov     r8d, esi; Size
0x180033310  mov     rdx, rdi; Src
0x180033313  mov     rcx, rax; void *
0x180033316  call    memcpy_0
0x18003331b  jmp     short loc_180033350
0x18003331d  mov     ebx, 0C000009Ah
0x180033322  mov     rcx, cs:WPP_GLOBAL_Control
0x180033329  lea     rax, WPP_GLOBAL_Control
0x180033330  cmp     rcx, rax
0x180033333  jz      short loc_180033350
0x180033335  test    byte ptr [rcx+1Ch], 1
0x180033339  jz      short loc_180033350
0x18003333b  mov     rcx, [rcx+10h]
0x18003333f  lea     r8, WPP_5a1eec0057703498b5d13460810c8614_Traceguids
0x180033346  mov     edx, 15h
0x18003334b  call    WPP_SF_
0x180033350  mov     rsi, [rsp+28h+arg_8]
0x180033355  mov     eax, ebx
0x180033357  mov     rbx, [rsp+28h+arg_0]
0x18003335c  add     rsp, 20h
0x180033360  pop     rdi
0x180033361  retn
```

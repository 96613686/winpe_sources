# RemoveDeviceInfoEntry

- ea: `0x180032fc8`
- end: `0x1800330a2`
- name: `RemoveDeviceInfoEntry`
- size: `218`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180017be0`
- `0x180024fc8`

## callees

- `0x18002a064`
- `0x180032fc8`
- `0x18003fb88`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18003308d`
- `KERNEL32!LeaveCriticalSection` at `0x18003308d`
- `KERNEL32!EnterCriticalSection` at `0x180032fe1`
- `KERNEL32!EnterCriticalSection` at `0x180032fe1`

## pseudocode

```c
__int64 __fastcall RemoveDeviceInfoEntry(unsigned int a1, int a2)
{
  _DWORD *v4; // rbx
  int v5; // esi
  int v6; // edi
  _DWORD *v7; // r14
  char *v8; // rcx
  __int64 v10; // [rsp+70h] [rbp+18h]

  EnterCriticalSection(&gMgmtCritSec);
  v4 = gpPhoneInfoList;
  if ( a1 )
    v4 = gpLineInfoList;
  if ( v4 )
  {
    v5 = v4[3];
    v6 = a2;
    if ( a2 >= v5 )
      v6 = v5 - 1;
    v7 = &v4[8 * v6 + 6 + 2 * v6];
    if ( v6 >= 0 )
    {
      while ( 1 )
      {
        HIDWORD(v10) = *v7;
        LODWORD(v10) = v7[1];
        if ( a2 == (unsigned int)GetDeviceIDFromPermanentID(v10, a1) )
          break;
        v7 -= 10;
        if ( --v6 < 0 )
          goto LABEL_13;
      }
      if ( v6 < v5 - 1 )
      {
        v8 = (char *)&v4[8 * v6 + 6 + 2 * v6];
        memmove_0(v8, v8 + 40, 40LL * (v5 - v6 - 1));
      }
      v4[4] -= 40;
      --v4[3];
    }
  }
LABEL_13:
  LeaveCriticalSection(&gMgmtCritSec);
  return 0;
}

```

## disassembly

```asm
0x180032fc8  push    rbx
0x180032fca  push    rbp
0x180032fcb  push    rsi
0x180032fcc  push    rdi
0x180032fcd  push    r14
0x180032fcf  push    r15
0x180032fd1  sub     rsp, 28h
0x180032fd5  mov     r15d, ecx
0x180032fd8  mov     ebp, edx
0x180032fda  lea     rcx, gMgmtCritSec; lpCriticalSection
0x180032fe1  call    cs:__imp_EnterCriticalSection
0x180032fe7  mov     rbx, cs:gpPhoneInfoList
0x180032fee  test    r15d, r15d
0x180032ff1  cmovnz  rbx, cs:gpLineInfoList
0x180032ff9  test    rbx, rbx
0x180032ffc  jz      loc_180033086
0x180033002  mov     esi, [rbx+0Ch]
0x180033005  mov     edi, ebp
0x180033007  cmp     ebp, esi
0x180033009  jl      short loc_18003300E
0x18003300b  lea     edi, [rsi-1]
0x18003300e  movsxd  rax, edi
0x180033011  lea     r14, ds:3[rax*4]
0x180033019  add     r14, rax
0x18003301c  lea     r14, [rbx+r14*8]
0x180033020  test    edi, edi
0x180033022  js      short loc_180033086
0x180033024  mov     eax, [r14]
0x180033027  mov     edx, r15d
0x18003302a  mov     dword ptr [rsp+58h+arg_10+4], eax
0x18003302e  mov     eax, [r14+4]
0x180033032  mov     dword ptr [rsp+58h+arg_10], eax
0x180033036  mov     rcx, [rsp+58h+arg_10]
0x18003303b  call    GetDeviceIDFromPermanentID
0x180033040  cmp     ebp, eax
0x180033042  jz      short loc_18003304F
0x180033044  sub     r14, 28h ; '('
0x180033048  sub     edi, 1
0x18003304b  jns     short loc_180033024
0x18003304d  jmp     short loc_180033086
0x18003304f  lea     eax, [rsi-1]
0x180033052  cmp     edi, eax
0x180033054  jge     short loc_18003307F
0x180033056  mov     eax, edi
0x180033058  sub     esi, edi
0x18003305a  lea     rcx, ds:3[rax*4]
0x180033062  add     rcx, rax
0x180033065  lea     eax, [rsi-1]
0x180033068  cdqe
0x18003306a  lea     rcx, [rbx+rcx*8]; void *
0x18003306e  lea     r8, [rax+rax*4]
0x180033072  shl     r8, 3; Size
0x180033076  lea     rdx, [rcx+28h]; Src
0x18003307a  call    memmove_0
0x18003307f  add     dword ptr [rbx+10h], 0FFFFFFD8h
0x180033083  dec     dword ptr [rbx+0Ch]
0x180033086  lea     rcx, gMgmtCritSec; lpCriticalSection
0x18003308d  call    cs:__imp_LeaveCriticalSection
0x180033093  xor     eax, eax
0x180033095  add     rsp, 28h
0x180033099  pop     r15
0x18003309b  pop     r14
0x18003309d  pop     rdi
0x18003309e  pop     rsi
0x18003309f  pop     rbp
0x1800330a0  pop     rbx
0x1800330a1  retn
```

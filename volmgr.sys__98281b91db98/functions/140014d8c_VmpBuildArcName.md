# VmpBuildArcName

- ea: `0x140014d8c`
- end: `0x140014e80`
- name: `VmpBuildArcName`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140011920`

## callees

- `0x140005540`
- `0x140014d8c`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140014e51`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140014e51`

## string_xrefs

- `0x140014e48`: `\Registry\Machine\System\CurrentControlSet\Control`

## pseudocode

```c
__int64 __fastcall VmpBuildArcName(__int64 a1, int a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 result; // rax
  const wchar_t *v6; // rax
  __int128 v7; // [rsp+38h] [rbp-59h] BYREF
  _QWORD v8[20]; // [rsp+48h] [rbp-49h] BYREF

  memset(v8, 0, 112);
  v7 = 0;
  *(_WORD *)a1 = 0;
  v3 = *(_QWORD *)(a1 + 8);
  *(_OWORD *)v3 = *(_OWORD *)L"\\ArcName\\";
  *(_WORD *)(v3 + 16) = aArcname[8];
  LOWORD(v3) = *(_WORD *)(a1 + 2) - 18;
  LODWORD(v8[1]) = 292;
  WORD1(v7) = v3;
  v4 = *(_QWORD *)(a1 + 8) + 18LL;
  LODWORD(v8[4]) = 0x1000000;
  *((_QWORD *)&v7 + 1) = v4;
  v8[3] = &v7;
  if ( a2 == 6 )
  {
    v6 = L"FirmwareBootDevice";
  }
  else
  {
    if ( a2 != 7 )
      return 3221225485LL;
    v6 = L"SystemBootDevice";
  }
  v8[2] = v6;
  result = RtlQueryRegistryValuesEx(0, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control", v8, 0, 0);
  if ( (int)result >= 0 )
    *(_WORD *)a1 = v7 + 18;
  return result;
}

```

## disassembly

```asm
0x140014d8c  mov     rax, rsp
0x140014d8f  push    rbp
0x140014d90  push    rbx
0x140014d91  push    rsi
0x140014d92  push    rdi
0x140014d93  lea     rbp, [rax-5Fh]
0x140014d97  sub     rsp, 0C8h
0x140014d9e  mov     ebx, dword ptr cs:aArcname+10h; "\\"
0x140014da4  mov     edi, edx
0x140014da6  xor     edx, edx; Val
0x140014da8  movaps  xmmword ptr [rax-38h], xmm6
0x140014dac  movups  xmm6, xmmword ptr cs:aArcname; "\\ArcName\\"
0x140014db3  mov     rsi, rcx
0x140014db6  mov     [rbp+57h+var_A0], 0
0x140014dbe  xorps   xmm0, xmm0
0x140014dc1  lea     rcx, [rbp+57h+var_98]; void *
0x140014dc5  lea     r8d, [rdx+68h]; Size
0x140014dc9  movups  [rbp+57h+var_B0], xmm0
0x140014dcd  call    memset
0x140014dd2  xor     eax, eax
0x140014dd4  mov     [rsi], ax
0x140014dd7  mov     rax, [rsi+8]
0x140014ddb  movups  xmmword ptr [rax], xmm6
0x140014dde  mov     [rax+10h], bx
0x140014de2  mov     ebx, 12h
0x140014de7  movzx   eax, word ptr [rsi+2]
0x140014deb  sub     ax, bx
0x140014dee  mov     [rbp+57h+var_98], 124h
0x140014df5  mov     word ptr [rbp+57h+var_B0+2], ax
0x140014df9  mov     rax, [rsi+8]
0x140014dfd  add     rax, rbx
0x140014e00  mov     [rbp+57h+var_80], 1000000h
0x140014e07  mov     qword ptr [rbp+57h+var_B0+8], rax
0x140014e0b  lea     rax, [rbp+57h+var_B0]
0x140014e0f  mov     [rbp+57h+var_88], rax
0x140014e13  sub     edi, 6
0x140014e16  jz      short loc_140014E2D
0x140014e18  cmp     edi, 1
0x140014e1b  jz      short loc_140014E24
0x140014e1d  mov     eax, 0C000000Dh
0x140014e22  jmp     short loc_140014E6B
0x140014e24  lea     rax, aSystembootdevi; "SystemBootDevice"
0x140014e2b  jmp     short loc_140014E34
0x140014e2d  lea     rax, aFirmwarebootde; "FirmwareBootDevice"
0x140014e34  xor     r9d, r9d
0x140014e37  mov     [rbp+57h+var_90], rax
0x140014e3b  lea     r8, [rbp+57h+var_A0]
0x140014e3f  mov     qword ptr [rsp+20h], 0
0x140014e48  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140014e4f  xor     ecx, ecx
0x140014e51  call    cs:__imp_RtlQueryRegistryValuesEx
0x140014e58  nop     dword ptr [rax+rax+00h]
0x140014e5d  test    eax, eax
0x140014e5f  js      short loc_140014E6B
0x140014e61  movzx   ecx, word ptr [rbp+57h+var_B0]
0x140014e65  add     cx, bx
0x140014e68  mov     [rsi], cx
0x140014e6b  movaps  xmm6, [rsp+0E0h+var_38+8]
0x140014e73  add     rsp, 0C8h
0x140014e7a  pop     rdi
0x140014e7b  pop     rsi
0x140014e7c  pop     rbx
0x140014e7d  pop     rbp
0x140014e7e  retn
```

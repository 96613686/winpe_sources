# TpmApiCreateCmdBuf

- ea: `0x1400342a4`
- end: `0x14003438f`
- name: `TpmApiCreateCmdBuf`
- size: `235`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140033400`
- `0x140033bd8`
- `0x140034398`

## callees

- `0x140032c60`
- `0x140032c88`
- `0x1400342a4`

## pseudocode

```c
__int64 __fastcall TpmApiCreateCmdBuf(__int64 a1, _QWORD *a2)
{
  int v4; // ebx
  __int64 v5; // r8
  _QWORD *v6; // rax
  _QWORD *v8; // [rsp+40h] [rbp+18h] BYREF
  __int64 v9; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  v8 = 0;
  v4 = TpmApiCallbackAlloc(a1, 4096, &v9);
  if ( v4 < 0 || (v4 = TpmApiCallbackAlloc(a1, 48, &v8), v4 < 0) )
  {
    v5 = v9;
  }
  else
  {
    v5 = v9;
    if ( v9 )
    {
      v6 = v8;
      if ( v8 )
      {
        *v8 = 4096;
        v6[1] = v5;
        v6[2] = 0;
        v6[3] = v5;
        v6[4] = 0;
        v6[5] = 0;
        v4 = 0;
        v5 = 0;
        *a2 = v8;
        v9 = 0;
        v8 = 0;
      }
      else
      {
        v4 = -2144796413;
      }
    }
    else
    {
      v4 = -2144796412;
    }
  }
  TpmApiCallbackFree(a1, 4096, v5);
  TpmApiCallbackFree(a1, 48, v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400342a4  mov     rax, rsp
0x1400342a7  mov     [rax+8], rbx
0x1400342ab  mov     [rax+10h], rsi
0x1400342af  push    rdi
0x1400342b0  sub     rsp, 20h
0x1400342b4  mov     rsi, rdx
0x1400342b7  mov     qword ptr [rax+20h], 0
0x1400342bf  mov     edx, 1000h
0x1400342c4  mov     qword ptr [rax+18h], 0
0x1400342cc  lea     r8, [rax+20h]
0x1400342d0  mov     rdi, rcx
0x1400342d3  call    TpmApiCallbackAlloc
0x1400342d8  mov     ebx, eax
0x1400342da  test    eax, eax
0x1400342dc  js      short loc_140034358
0x1400342de  lea     r8, [rsp+28h+arg_10]
0x1400342e3  mov     edx, 30h ; '0'
0x1400342e8  mov     rcx, rdi
0x1400342eb  call    TpmApiCallbackAlloc
0x1400342f0  mov     ebx, eax
0x1400342f2  test    eax, eax
0x1400342f4  js      short loc_140034358
0x1400342f6  mov     r8, [rsp+28h+arg_18]
0x1400342fb  test    r8, r8
0x1400342fe  jnz     short loc_140034307
0x140034300  mov     ebx, 80290104h
0x140034305  jmp     short loc_14003435D
0x140034307  mov     rax, [rsp+28h+arg_10]
0x14003430c  test    rax, rax
0x14003430f  jnz     short loc_140034318
0x140034311  mov     ebx, 80290103h
0x140034316  jmp     short loc_14003435D
0x140034318  mov     qword ptr [rax], 1000h
0x14003431f  mov     [rax+8], r8
0x140034323  mov     qword ptr [rax+10h], 0
0x14003432b  mov     [rax+18h], r8
0x14003432f  mov     qword ptr [rax+20h], 0
0x140034337  mov     qword ptr [rax+28h], 0
0x14003433f  mov     rax, [rsp+28h+arg_10]
0x140034344  xor     ebx, ebx
0x140034346  xor     r8d, r8d
0x140034349  mov     [rsi], rax
0x14003434c  mov     [rsp+28h+arg_18], r8
0x140034351  mov     [rsp+28h+arg_10], rbx
0x140034356  jmp     short loc_14003435D
0x140034358  mov     r8, [rsp+28h+arg_18]
0x14003435d  mov     edx, 1000h
0x140034362  mov     rcx, rdi
0x140034365  call    TpmApiCallbackFree
0x14003436a  mov     r8, [rsp+28h+arg_10]
0x14003436f  mov     edx, 30h ; '0'
0x140034374  mov     rcx, rdi
0x140034377  call    TpmApiCallbackFree
0x14003437c  mov     rsi, [rsp+28h+arg_8]
0x140034381  mov     eax, ebx
0x140034383  mov     rbx, [rsp+28h+arg_0]
0x140034388  add     rsp, 20h
0x14003438c  pop     rdi
0x14003438d  retn
```

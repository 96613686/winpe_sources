# UdfPowTrackInfoUpdate

- ea: `0x140037f1c`
- end: `0x140038034`
- name: `UdfPowTrackInfoUpdate`
- size: `280`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000a0ec`
- `0x140017c08`
- `0x14001a3a4`

## callees

- `0x14000cad4`
- `0x1400138ec`
- `0x14001bc30`
- `0x14002fe08`
- `0x140037e4c`
- `0x140037f1c`

## pseudocode

```c
__int64 __fastcall UdfPowTrackInfoUpdate(__int64 a1)
{
  int v1; // r14d
  unsigned __int16 i; // bp
  _DWORD *v4; // rsi
  int TrackInfo; // edi
  _OWORD v7[2]; // [rsp+20h] [rbp-48h] BYREF
  int v8; // [rsp+40h] [rbp-28h]

  v1 = 0;
  v8 = 0;
  memset(v7, 0, sizeof(v7));
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 896); ++i )
  {
    v4 = (_DWORD *)(*(_QWORD *)(a1 + 904) + 36LL * i);
    TrackInfo = UdfReadTrackInfo(*(_QWORD *)(a1 + 24), *(unsigned __int16 *)v4, v7, 36);
    if ( TrackInfo < 0 )
      goto LABEL_6;
    UdfPowTrackInfoSave(v4, v7);
    v1 += v4[4];
    *(_DWORD *)(a1 + 2552) = v4[5];
    *(_DWORD *)(a1 + 2556) = v4[7];
  }
  *(_DWORD *)(a1 + 668) = v1;
  TrackInfo = UdfPowAssignTrackInfo(a1);
  if ( TrackInfo >= 0 )
    return (unsigned int)TrackInfo;
LABEL_6:
  *(_DWORD *)(a1 + 48) |= 0x4010u;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 11, WPP_4e743084496f34642ec7d35f53c51c7f_Traceguids);
  }
  *(_DWORD *)(a1 + 668) = 0;
  return (unsigned int)TrackInfo;
}

```

## disassembly

```asm
0x140037f1c  mov     [rsp+arg_8], rbx
0x140037f21  mov     [rsp+arg_10], rbp
0x140037f26  push    rsi
0x140037f27  push    rdi
0x140037f28  push    r14
0x140037f2a  sub     rsp, 50h
0x140037f2e  mov     rax, cs:__security_cookie
0x140037f35  xor     rax, rsp
0x140037f38  mov     [rsp+68h+var_20], rax
0x140037f3d  xorps   xmm0, xmm0
0x140037f40  xor     eax, eax
0x140037f42  xor     r14d, r14d
0x140037f45  mov     [rsp+68h+var_28], eax
0x140037f49  movups  [rsp+68h+var_48], xmm0
0x140037f4e  xor     ebp, ebp
0x140037f50  mov     rbx, rcx
0x140037f53  movups  [rsp+68h+var_38], xmm0
0x140037f58  movzx   eax, bp
0x140037f5b  cmp     eax, [rbx+380h]
0x140037f61  jnb     short loc_140037FBA
0x140037f63  movzx   eax, bp
0x140037f66  lea     r8, [rsp+68h+var_48]
0x140037f6b  mov     r9d, 24h ; '$'
0x140037f71  lea     rcx, [rax+rax*8]
0x140037f75  mov     rax, [rbx+388h]
0x140037f7c  lea     rsi, [rax+rcx*4]
0x140037f80  mov     rcx, [rbx+18h]
0x140037f84  movzx   edx, word ptr [rsi]
0x140037f87  call    UdfReadTrackInfo
0x140037f8c  mov     edi, eax
0x140037f8e  test    eax, eax
0x140037f90  js      short loc_140037FCF
0x140037f92  lea     rdx, [rsp+68h+var_48]
0x140037f97  mov     rcx, rsi
0x140037f9a  call    UdfPowTrackInfoSave
0x140037f9f  mov     eax, [rsi+14h]
0x140037fa2  add     r14d, [rsi+10h]
0x140037fa6  mov     [rbx+9F8h], eax
0x140037fac  inc     bp
0x140037faf  mov     eax, [rsi+1Ch]
0x140037fb2  mov     [rbx+9FCh], eax
0x140037fb8  jmp     short loc_140037F58
0x140037fba  mov     rcx, rbx
0x140037fbd  mov     [rbx+29Ch], r14d
0x140037fc4  call    UdfPowAssignTrackInfo
0x140037fc9  mov     edi, eax
0x140037fcb  test    eax, eax
0x140037fcd  jns     short loc_14003800F
0x140037fcf  or      dword ptr [rbx+30h], 4010h
0x140037fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140037fdd  lea     rax, WPP_GLOBAL_Control
0x140037fe4  cmp     rcx, rax
0x140037fe7  jz      short loc_140038005
0x140037fe9  mov     eax, [rcx+2Ch]
0x140037fec  test    al, 1
0x140037fee  jz      short loc_140038005
0x140037ff0  mov     rcx, [rcx+18h]
0x140037ff4  lea     r8, WPP_4e743084496f34642ec7d35f53c51c7f_Traceguids
0x140037ffb  mov     edx, 0Bh
0x140038000  call    WPP_SF_
0x140038005  mov     dword ptr [rbx+29Ch], 0
0x14003800f  mov     eax, edi
0x140038011  mov     rcx, [rsp+68h+var_20]
0x140038016  xor     rcx, rsp; StackCookie
0x140038019  call    __security_check_cookie
0x14003801e  lea     r11, [rsp+68h+var_18]
0x140038023  mov     rbx, [r11+28h]
0x140038027  mov     rbp, [r11+30h]
0x14003802b  mov     rsp, r11
0x14003802e  pop     r14
0x140038030  pop     rdi
0x140038031  pop     rsi
0x140038032  retn
```

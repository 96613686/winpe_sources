# UdfGetConfiguration

- ea: `0x14002e018`
- end: `0x14002e191`
- name: `UdfGetConfiguration`
- size: `377`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002fc98`
- `0x140058d88`

## callees

- `0x14000ca10`
- `0x14001093c`
- `0x14002e018`
- `0x140054560`

## pseudocode

```c
__int64 __fastcall UdfGetConfiguration(__int64 a1, __int64 a2, int a3, _BYTE *a4, unsigned int a5)
{
  __int64 result; // rax
  __int64 v9; // rcx
  unsigned int v10; // edi
  int v11; // eax
  unsigned int v12; // esi
  _DWORD v13[2]; // [rsp+60h] [rbp-48h] BYREF
  __int128 v14; // [rsp+68h] [rbp-40h]
  int v15; // [rsp+C0h] [rbp+18h]

  v13[0] = a3;
  v13[1] = 2;
  v14 = 0;
  result = UdfPerformDevIoCtrl(a1, 147544, a2, v13, 24, a4, 8);
  if ( (int)result >= 0 )
  {
    LOBYTE(v15) = a4[3];
    BYTE1(v15) = a4[2];
    BYTE2(v15) = a4[1];
    HIBYTE(v15) = *a4;
    v10 = v15 + 4;
    if ( (unsigned int)(v15 + 4) > 8 )
    {
      if ( v10 <= a5 )
      {
        v11 = UdfPerformDevIoCtrl(v9, 147544, a2, v13, 24, a4, v15 + 4);
        v12 = v11;
        if ( v11 < 0 )
        {
          if ( v11 == -1073741764 )
          {
            if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) != 0 )
            {
              WPP_SF_d(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                17,
                WPP_9fc1880bfcae3bc333ea8e1a40f594fb_Traceguids);
            }
            a4[10] &= ~1u;
            return 0;
          }
        }
        else if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) != 0 )
        {
          WPP_SF_dd(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            16,
            WPP_9fc1880bfcae3bc333ea8e1a40f594fb_Traceguids,
            v10,
            a3);
        }
        return v12;
      }
      else
      {
        return 3221225507LL;
      }
    }
    else
    {
      return 3221225532LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002e018  mov     rax, rsp
0x14002e01b  push    rbx
0x14002e01c  push    rbp
0x14002e01d  push    rsi
0x14002e01e  push    rdi
0x14002e01f  sub     rsp, 88h
0x14002e026  mov     [rax-48h], r8d
0x14002e02a  mov     rbx, r9
0x14002e02d  mov     dword ptr [rax-44h], 2
0x14002e034  lea     rax, [rax-58h]
0x14002e038  mov     [rsp+0A8h+var_60], rax
0x14002e03d  lea     r9, [rsp+0A8h+var_48]
0x14002e042  mov     [rsp+0A8h+var_68], 0
0x14002e047  xorps   xmm0, xmm0
0x14002e04a  movdqu  xmmword ptr [rax+18h], xmm0
0x14002e04f  mov     ebp, r8d
0x14002e052  mov     [rsp+0A8h+var_78], 8
0x14002e05a  mov     rsi, rdx
0x14002e05d  mov     [rsp+0A8h+var_80], rbx
0x14002e062  mov     r8, rdx
0x14002e065  mov     [rsp+0A8h+var_88], 18h
0x14002e06d  mov     edx, 24058h
0x14002e072  call    UdfPerformDevIoCtrl
0x14002e077  test    eax, eax
0x14002e079  js      loc_14002E184
0x14002e07f  mov     al, [rbx+3]
0x14002e082  mov     byte ptr [rsp+0A8h+arg_10], al
0x14002e089  mov     al, [rbx+2]
0x14002e08c  mov     byte ptr [rsp+0A8h+arg_10+1], al
0x14002e093  mov     al, [rbx+1]
0x14002e096  mov     byte ptr [rsp+0A8h+arg_10+2], al
0x14002e09d  mov     al, [rbx]
0x14002e09f  mov     byte ptr [rsp+0A8h+arg_10+3], al
0x14002e0a6  mov     edi, [rsp+0A8h+arg_10]
0x14002e0ad  add     edi, 4
0x14002e0b0  cmp     edi, 8
0x14002e0b3  ja      short loc_14002E0BF
0x14002e0b5  mov     eax, 0C000003Ch
0x14002e0ba  jmp     loc_14002E184
0x14002e0bf  cmp     edi, [rsp+0A8h+arg_20]
0x14002e0c6  jbe     short loc_14002E0D2
0x14002e0c8  mov     eax, 0C0000023h
0x14002e0cd  jmp     loc_14002E184
0x14002e0d2  lea     rax, [rsp+0A8h+var_58]
0x14002e0d7  mov     r8, rsi
0x14002e0da  mov     [rsp+0A8h+var_60], rax
0x14002e0df  lea     r9, [rsp+0A8h+var_48]
0x14002e0e4  mov     [rsp+0A8h+var_68], 0
0x14002e0e9  mov     edx, 24058h
0x14002e0ee  mov     [rsp+0A8h+var_78], edi
0x14002e0f2  mov     [rsp+0A8h+var_80], rbx
0x14002e0f7  mov     [rsp+0A8h+var_88], 18h
0x14002e0ff  call    UdfPerformDevIoCtrl
0x14002e104  mov     esi, eax
0x14002e106  test    eax, eax
0x14002e108  js      short loc_14002E143
0x14002e10a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e111  lea     rax, WPP_GLOBAL_Control
0x14002e118  cmp     rcx, rax
0x14002e11b  jz      short loc_14002E182
0x14002e11d  mov     edx, [rcx+2Ch]
0x14002e120  test    dl, 40h
0x14002e123  jz      short loc_14002E182
0x14002e125  mov     rcx, [rcx+18h]
0x14002e129  lea     r8, WPP_9fc1880bfcae3bc333ea8e1a40f594fb_Traceguids
0x14002e130  mov     edx, 10h
0x14002e135  mov     [rsp+0A8h+var_88], ebp
0x14002e139  mov     r9d, edi
0x14002e13c  call    WPP_SF_dd
0x14002e141  jmp     short loc_14002E182
0x14002e143  cmp     eax, 0C000003Ch
0x14002e148  jnz     short loc_14002E182
0x14002e14a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e151  lea     rax, WPP_GLOBAL_Control
0x14002e158  cmp     rcx, rax
0x14002e15b  jz      short loc_14002E17C
0x14002e15d  mov     eax, [rcx+2Ch]
0x14002e160  test    al, 40h
0x14002e162  jz      short loc_14002E17C
0x14002e164  mov     rcx, [rcx+18h]
0x14002e168  lea     r8, WPP_9fc1880bfcae3bc333ea8e1a40f594fb_Traceguids
0x14002e16f  mov     edx, 11h
0x14002e174  mov     r9d, ebp
0x14002e177  call    WPP_SF_d
0x14002e17c  and     byte ptr [rbx+0Ah], 0FEh
0x14002e180  xor     esi, esi
0x14002e182  mov     eax, esi
0x14002e184  add     rsp, 88h
0x14002e18b  pop     rdi
0x14002e18c  pop     rsi
0x14002e18d  pop     rbp
0x14002e18e  pop     rbx
0x14002e18f  retn
```

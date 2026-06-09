# WcnWlanOpenHandle(void * *)

- ea: `0x1800510b8`
- end: `0x1800511f2`
- name: `?WcnWlanOpenHandle@@YAJPEAPEAX@Z`
- size: `314`
- prototype: `__int64 __fastcall(PHANDLE phClientHandle)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800454a0`
- `0x180047544`
- `0x180048594`
- `0x18004c224`

## callees

- `0x180004f2c`
- `0x180004fb8`
- `0x180005014`
- `0x1800510b8`
- `0x180053004`

## import_xrefs

- `wlanapi!WlanOpenHandle` at `0x180051152`
- `wlanapi!WlanOpenHandle` at `0x180051152`

## pseudocode

```c
__int64 __fastcall WcnWlanOpenHandle(PHANDLE phClientHandle)
{
  _QWORD *v2; // r10
  const char *Indent; // rax
  __int64 v4; // r10
  signed int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  _BYTE *v9; // r10
  unsigned int v10; // eax
  __int64 v11; // r10
  DWORD pdwNegotiatedVersion; // [rsp+40h] [rbp+8h] BYREF

  pdwNegotiatedVersion = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v4 + 16), 15, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids, Indent);
    v2 = WPP_GLOBAL_Control;
  }
  if ( phClientHandle )
  {
    v6 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, phClientHandle);
    if ( v6 )
    {
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      else
        v7 = v6;
      v8 = v7 | 0x80000000;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v8;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_18:
        if ( v9 != (_BYTE *)&WPP_GLOBAL_Control && ((v8 & 0x80000000) != 0 || v9[25] >= 6u) )
        {
          v10 = (unsigned int)GetIndent(-1);
          WPP_SF_sd(*(_QWORD *)(v11 + 16), 18, (unsigned int)WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids, v10, v8);
        }
        return v8;
      }
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids,
        (unsigned int)v6,
        v8);
    }
    else
    {
      v8 = 0;
      ++g_WlanHandleOpenCount;
    }
    v9 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 2u )
    WPP_SF_s(v2[2], 16, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids, "phWlanHandle");
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800510b8  mov     [rsp+arg_8], rbx
0x1800510bd  push    rdi
0x1800510be  sub     rsp, 30h
0x1800510c2  mov     rbx, rcx
0x1800510c5  mov     [rsp+38h+pdwNegotiatedVersion], 0
0x1800510cd  mov     r10, cs:WPP_GLOBAL_Control
0x1800510d4  lea     rdi, WPP_GLOBAL_Control
0x1800510db  cmp     r10, rdi
0x1800510de  jz      short loc_180051110
0x1800510e0  cmp     byte ptr [r10+19h], 6
0x1800510e5  jb      short loc_180051110
0x1800510e7  mov     ecx, 1; int
0x1800510ec  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800510f1  mov     rcx, [r10+10h]
0x1800510f5  lea     r8, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids
0x1800510fc  mov     edx, 0Fh
0x180051101  mov     r9, rax
0x180051104  call    WPP_SF_s
0x180051109  mov     r10, cs:WPP_GLOBAL_Control
0x180051110  test    rbx, rbx
0x180051113  jnz     short loc_180051145
0x180051115  cmp     r10, rdi
0x180051118  jz      short loc_18005113B
0x18005111a  cmp     byte ptr [r10+19h], 2
0x18005111f  jb      short loc_18005113B
0x180051121  mov     rcx, [r10+10h]
0x180051125  lea     edx, [rbx+10h]
0x180051128  lea     r9, aPhwlanhandle; "phWlanHandle"
0x18005112f  lea     r8, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids
0x180051136  call    WPP_SF_s
0x18005113b  mov     eax, 80004003h
0x180051140  jmp     loc_1800511E7
0x180051145  xor     edx, edx; pReserved
0x180051147  lea     r8, [rsp+38h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18005114c  mov     r9, rbx; phClientHandle
0x18005114f  lea     ecx, [rdx+2]; dwClientVersion
0x180051152  call    cs:__imp_WlanOpenHandle
0x180051158  test    eax, eax
0x18005115a  jz      short loc_1800511A2
0x18005115c  jg      short loc_180051162
0x18005115e  mov     ebx, eax
0x180051160  jmp     short loc_18005116B
0x180051162  movzx   ebx, ax
0x180051165  or      ebx, 80070000h
0x18005116b  or      ebx, 80000000h
0x180051171  mov     r10, cs:WPP_GLOBAL_Control
0x180051178  cmp     r10, rdi
0x18005117b  jz      short loc_1800511E5
0x18005117d  cmp     byte ptr [r10+19h], 2
0x180051182  jb      short loc_1800511B1
0x180051184  mov     rcx, [r10+10h]
0x180051188  lea     r8, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids
0x18005118f  mov     edx, 11h
0x180051194  mov     [rsp+38h+var_18], ebx
0x180051198  mov     r9d, eax
0x18005119b  call    WPP_SF_Dd
0x1800511a0  jmp     short loc_1800511AA
0x1800511a2  xor     ebx, ebx
0x1800511a4  inc     cs:?g_WlanHandleOpenCount@@3JA; long g_WlanHandleOpenCount
0x1800511aa  mov     r10, cs:WPP_GLOBAL_Control
0x1800511b1  cmp     r10, rdi
0x1800511b4  jz      short loc_1800511E5
0x1800511b6  test    ebx, ebx
0x1800511b8  js      short loc_1800511C1
0x1800511ba  cmp     byte ptr [r10+19h], 6
0x1800511bf  jb      short loc_1800511E5
0x1800511c1  or      ecx, 0FFFFFFFFh; int
0x1800511c4  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800511c9  mov     rcx, [r10+10h]
0x1800511cd  lea     r8, WPP_0370c37c8d5e3da96dcc11a549a1fe27_Traceguids
0x1800511d4  mov     edx, 12h
0x1800511d9  mov     [rsp+38h+var_18], ebx
0x1800511dd  mov     r9, rax
0x1800511e0  call    WPP_SF_sd
0x1800511e5  mov     eax, ebx
0x1800511e7  mov     rbx, [rsp+38h+arg_8]
0x1800511ec  add     rsp, 30h
0x1800511f0  pop     rdi
0x1800511f1  retn
```

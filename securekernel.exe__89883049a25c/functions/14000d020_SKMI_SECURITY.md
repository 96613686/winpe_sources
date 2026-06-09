# SKMI_SECURITY

- ea: `0x14000d020`
- end: `0x14000d059`
- name: `SKMI_SECURITY`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `57`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001120`
- `0x140002fac`
- `0x140009a90`
- `0x14000a320`
- `0x14000b2c0`
- `0x14000bab0`
- `0x14000ccb0`
- `0x140012750`
- `0x140014dd0`
- `0x14001b520`
- `0x14002ba88`
- `0x140031fbc`
- `0x14003a10c`
- `0x14004d104`
- `0x14005449c`
- `0x140055000`
- `0x14005a0f8`
- `0x14005f31c`
- `0x140062334`
- `0x140063694`
- `0x140063a80`
- `0x140066464`
- `0x14006d8e4`
- `0x14006dcfc`
- `0x14006e2c4`
- `0x14006e3b4`
- `0x14006e418`
- `0x14006e520`
- `0x14006e578`
- `0x14006e5dc`
- `0x14006e6e4`
- `0x14006e730`
- `0x14006e794`
- `0x14006e870`
- `0x14006e8b4`
- `0x14006e900`
- `0x14006e9c8`
- `0x14006eae4`
- `0x14006eb54`
- `0x14006ec08`
- `0x14006ec6c`
- `0x14006f704`
- `0x14006fcdc`
- `0x1400709d8`
- `0x140070cd8`
- `0x140072594`
- `0x140072884`
- `0x140072b1c`
- `0x140074200`
- `0x140074af0`

## callees

- `0x14000d020`
- `0x1400714d4`

## pseudocode

```c
__int64 __fastcall SKMI_SECURITY(int a1)
{
  __int64 result; // rax
  _OWORD v2[3]; // [rsp+20h] [rbp-48h] BYREF
  int v3; // [rsp+50h] [rbp-18h]

  result = 0;
  memset(v2, 0, sizeof(v2));
  v3 = 0;
  if ( SkmiFailureLog )
  {
    DWORD2(v2[0]) = a1;
    return SkmiLogFailure(v2);
  }
  return result;
}

```

## disassembly

```asm
0x14000d020  sub     rsp, 68h
0x14000d024  xorps   xmm0, xmm0
0x14000d027  xor     eax, eax
0x14000d029  cmp     cs:SkmiFailureLog, rax
0x14000d030  movups  [rsp+68h+var_48], xmm0
0x14000d035  mov     [rsp+68h+var_18], eax
0x14000d039  movups  [rsp+68h+var_38], xmm0
0x14000d03e  movups  [rsp+68h+var_28], xmm0
0x14000d043  jz      short loc_14000D053
0x14000d045  mov     dword ptr [rsp+68h+var_48+8], ecx
0x14000d049  lea     rcx, [rsp+68h+var_48]
0x14000d04e  call    SkmiLogFailure
0x14000d053  add     rsp, 68h
0x14000d057  retn
```

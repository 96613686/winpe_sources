# CWerComReport::_get_IsWow64(int *)

- ea: `0x180010650`
- end: `0x18001072d`
- name: `?_get_IsWow64@CWerComReport@@QEAAJPEAH@Z`
- size: `221`
- prototype: `__int64 __fastcall(CWerComReport *__hidden this, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800116e0`

## callees

- `0x180006c9c`
- `0x18000e35c`
- `0x180010650`

## import_xrefs

- `wer!WerpGetWow64Process` at `0x1800106d1`
- `wer!WerpGetWow64Process` at `0x1800106d1`

## pseudocode

```c
__int64 __fastcall CWerComReport::_get_IsWow64(CWerComReport *this, int *a2)
{
  int WerApiLock; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD v9[3]; // [rsp+20h] [rbp-18h] BYREF
  int v10; // [rsp+50h] [rbp+18h] BYREF
  int v11; // [rsp+58h] [rbp+20h] BYREF

  v9[0] = 0;
  WerApiLock = CWerApiAutoLock::TryGetWerApiLock((CWerApiAutoLock *)v9, this);
  if ( WerApiLock >= 0 )
  {
    v7 = *((_QWORD *)this + 4);
    v11 = 0;
    v10 = 0;
    WerApiLock = WerpGetWow64Process(v7, &v11, &v10);
    if ( WerApiLock >= 0 )
    {
      *a2 = v11 != v10;
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 29;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 28;
LABEL_5:
      WPP_SF_d(v5[2], v6, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids, (unsigned int)WerApiLock);
    }
  }
  if ( v9[0] )
    _InterlockedExchange((volatile __int32 *)(v9[0] + 48LL), 0);
  return (unsigned int)WerApiLock;
}

```

## disassembly

```asm
0x180010650  mov     rax, rsp
0x180010653  mov     [rax+8], rbx
0x180010657  mov     [rax+10h], rsi
0x18001065b  push    rdi
0x18001065c  sub     rsp, 30h
0x180010660  mov     rsi, rdx
0x180010663  mov     qword ptr [rax-18h], 0
0x18001066b  mov     rdx, rcx; struct CWerComReport *
0x18001066e  mov     rdi, rcx
0x180010671  lea     rcx, [rax-18h]; this
0x180010675  call    ?TryGetWerApiLock@CWerApiAutoLock@@QEAAJPEAVCWerComReport@@@Z; CWerApiAutoLock::TryGetWerApiLock(CWerComReport *)
0x18001067a  mov     ebx, eax
0x18001067c  test    eax, eax
0x18001067e  jns     short loc_1800106B3
0x180010680  mov     rcx, cs:WPP_GLOBAL_Control
0x180010687  lea     rdx, WPP_GLOBAL_Control
0x18001068e  cmp     rcx, rdx
0x180010691  jz      short loc_18001070C
0x180010693  test    byte ptr [rcx+1Ch], 1
0x180010697  jz      short loc_18001070C
0x180010699  mov     edx, 1Ch
0x18001069e  mov     rcx, [rcx+10h]
0x1800106a2  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x1800106a9  mov     r9d, ebx
0x1800106ac  call    WPP_SF_d
0x1800106b1  jmp     short loc_18001070C
0x1800106b3  mov     rcx, [rdi+20h]
0x1800106b7  lea     r8, [rsp+38h+arg_10]
0x1800106bc  lea     rdx, [rsp+38h+arg_18]
0x1800106c1  mov     [rsp+38h+arg_18], 0
0x1800106c9  mov     [rsp+38h+arg_10], 0
0x1800106d1  call    cs:__imp_WerpGetWow64Process
0x1800106d7  mov     ebx, eax
0x1800106d9  test    eax, eax
0x1800106db  jns     short loc_1800106FD
0x1800106dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106e4  lea     rdx, WPP_GLOBAL_Control
0x1800106eb  cmp     rcx, rdx
0x1800106ee  jz      short loc_18001070C
0x1800106f0  test    byte ptr [rcx+1Ch], 1
0x1800106f4  jz      short loc_18001070C
0x1800106f6  mov     edx, 1Dh
0x1800106fb  jmp     short loc_18001069E
0x1800106fd  mov     eax, [rsp+38h+arg_10]
0x180010701  xor     ecx, ecx
0x180010703  cmp     [rsp+38h+arg_18], eax
0x180010707  setnz   cl
0x18001070a  mov     [rsi], ecx
0x18001070c  mov     rax, [rsp+38h+var_18]
0x180010711  test    rax, rax
0x180010714  jz      short loc_18001071B
0x180010716  xor     ecx, ecx
0x180010718  xchg    ecx, [rax+30h]
0x18001071b  mov     rsi, [rsp+38h+arg_8]
0x180010720  mov     eax, ebx
0x180010722  mov     rbx, [rsp+38h+arg_0]
0x180010727  add     rsp, 30h
0x18001072b  pop     rdi
0x18001072c  retn
```

# SeqDeleteEvent

- ea: `0x180002c4c`
- end: `0x180002d0b`
- name: `SeqDeleteEvent`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000bf20`

## callees

- `0x180002250`
- `0x180002c4c`
- `0x180008abc`
- `0x18000bca4`
- `0x18001dc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c89`

## string_xrefs

- `0x180002c59`: `WdsDeleteEvent`
- `0x180002cc5`: `SeqDeleteEvent`
- `0x180002c97`: `WdsDeleteEvent - must pass in a WDS_QUEUE_POSITION from the iteration callback only!`

## pseudocode

```c
__int64 __fastcall SeqDeleteEvent(_QWORD *a1)
{
  __int64 result; // rax
  DWORD LastError; // ebx
  int *v4; // rax
  LPCWSTR lpModuleName; // [rsp+68h] [rbp+0h]

  result = IsWorkQueueAccessible(L"WdsDeleteEvent");
  if ( (_DWORD)result )
  {
    if ( (unsigned __int64)a1 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v4 = (int *)ConstructPartialMsgW(
                    0x30000B6u,
                    "WdsDeleteEvent - must pass in a WDS_QUEUE_POSITION from the iteration callback only!");
      WdsSetupLogMessageW(
        v4,
        589824,
        (__int64)L"D",
        0,
        0x1259u,
        L"onecore\\base\\ntsetup\\panther\\engine\\seq.c",
        L"SeqDeleteEvent",
        lpModuleName,
        LastError,
        0,
        0);
    }
    else
    {
      DeleteListItem(*a1, a1);
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180002c4c  mov     [rsp+arg_0], rbx
0x180002c51  push    rdi
0x180002c52  sub     rsp, 60h
0x180002c56  mov     rbx, rcx
0x180002c59  lea     rcx, aWdsdeleteevent_0; "WdsDeleteEvent"
0x180002c60  call    IsWorkQueueAccessible
0x180002c65  test    eax, eax
0x180002c67  jz      loc_180002CFF
0x180002c6d  lea     rax, [rbx-1]
0x180002c71  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002c75  ja      short loc_180002C84
0x180002c77  mov     rdx, rbx
0x180002c7a  mov     rcx, [rbx]
0x180002c7d  call    DeleteListItem
0x180002c82  jmp     short loc_180002CFA
0x180002c84  mov     rdi, [rsp+68h]
0x180002c89  call    cs:__imp_GetLastError
0x180002c90  nop     dword ptr [rax+rax+00h]
0x180002c95  mov     ebx, eax
0x180002c97  lea     rdx, aWdsdeleteevent_1; "WdsDeleteEvent - must pass in a WDS_QUE"...
0x180002c9e  mov     ecx, 30000B6h; unsigned int
0x180002ca3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180002ca8  mov     rcx, rax; int
0x180002cab  mov     [rsp+68h+var_18], 0; int
0x180002cb3  mov     [rsp+68h+var_20], 0; __int64
0x180002cbc  mov     [rsp+68h+var_28], ebx; int
0x180002cc0  mov     [rsp+68h+lpModuleName], rdi; lpModuleName
0x180002cc5  lea     rax, aSeqdeleteevent; "SeqDeleteEvent"
0x180002ccc  mov     [rsp+68h+var_38], rax; __int64
0x180002cd1  lea     rax, aOnecoreBaseNts_3; "onecore\\base\\ntsetup\\panther\\engine"...
0x180002cd8  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180002cdd  mov     [rsp+68h+var_48], 1259h; int
0x180002ce5  xor     r9d, r9d; int
0x180002ce8  lea     r8, aD_1; "D"
0x180002cef  mov     edx, 90000h; int
0x180002cf4  call    WdsSetupLogMessageW
0x180002cf9  nop
0x180002cfa  mov     eax, 1
0x180002cff  mov     rbx, [rsp+68h+arg_0]
0x180002d04  add     rsp, 60h
0x180002d08  pop     rdi
0x180002d09  retn
0x180027ab6  push    rbp
0x180027ab8  sub     rsp, 60h
0x180027abc  mov     rbp, rdx
0x180027abf  add     rsp, 60h
0x180027ac3  pop     rbp
0x180027ac4  retn
```

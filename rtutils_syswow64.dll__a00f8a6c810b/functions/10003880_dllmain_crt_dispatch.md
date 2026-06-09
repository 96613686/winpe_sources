# dllmain_crt_dispatch

- ea: `0x10003880`
- end: `0x100038d5`
- name: `dllmain_crt_dispatch`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x10003aa8`

## callees

- `0x10003880`
- `0x100038db`
- `0x100039eb`
- `0x10003e38`
- `0x10003e5d`

## pseudocode

```c
int __stdcall dllmain_crt_dispatch(int a1, int a2, int a3)
{
  int result; // eax

  switch ( a2 )
  {
    case 0:
      return dllmain_crt_process_detach(a3 != 0);
    case 1:
      return dllmain_crt_process_attach(a1, a3);
    case 2:
      LOBYTE(result) = __scrt_dllmain_crt_thread_attach();
      break;
    case 3:
      LOBYTE(result) = __scrt_dllmain_crt_thread_detach();
      break;
    default:
      return 1;
  }
  return (unsigned __int8)result;
}

```

## disassembly

```asm
0x10003880  mov     edi, edi
0x10003882  push    ebp
0x10003883  mov     ebp, esp
0x10003885  mov     eax, [ebp+arg_4]
0x10003888  sub     eax, 0
0x1000388b  jz      short loc_100038C0
0x1000388d  sub     eax, 1
0x10003890  jz      short loc_100038B2
0x10003892  sub     eax, 1
0x10003895  jz      short loc_100038A8
0x10003897  sub     eax, 1
0x1000389a  jz      short loc_100038A1
0x1000389c  xor     eax, eax
0x1000389e  inc     eax
0x1000389f  jmp     short loc_100038D1
0x100038a1  call    ___scrt_dllmain_crt_thread_detach
0x100038a6  jmp     short loc_100038AD
0x100038a8  call    ___scrt_dllmain_crt_thread_attach
0x100038ad  movzx   eax, al
0x100038b0  jmp     short loc_100038D1
0x100038b2  push    [ebp+arg_8]
0x100038b5  push    [ebp+arg_0]
0x100038b8  call    dllmain_crt_process_attach
0x100038bd  pop     ecx
0x100038be  jmp     short loc_100038D0
0x100038c0  cmp     [ebp+arg_8], 0
0x100038c4  setnz   al
0x100038c7  movzx   eax, al
0x100038ca  push    eax
0x100038cb  call    dllmain_crt_process_detach
0x100038d0  pop     ecx
0x100038d1  pop     ebp
0x100038d2  retn    0Ch
```

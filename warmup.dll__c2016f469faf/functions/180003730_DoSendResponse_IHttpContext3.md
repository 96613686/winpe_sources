# DoSendResponse(IHttpContext3 *)

- ea: `0x180003730`
- end: `0x180003810`
- name: `?DoSendResponse@@YA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext3@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000268c`

## callees

- `0x180003730`
- `0x180006010`

## string_xrefs

- `0x1800037a0`: `No-Cache`

## pseudocode

```c
__int64 __fastcall DoSendResponse(__int64 *a1)
{
  __int64 v1; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  int v6; // [rsp+50h] [rbp+8h] BYREF
  _BYTE *v7; // [rsp+58h] [rbp+10h] BYREF

  v1 = *a1;
  v7 = 0;
  v6 = 0;
  if ( (*(int (__fastcall **)(__int64 *, const char *, _BYTE **, int *))(v1 + 120))(a1, "APP_WARMING_UP", &v7, &v6) < 0 )
    return 0;
  if ( *v7 != 49 )
    return 0;
  v3 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 32))(a1);
  if ( (*(int (__fastcall **)(__int64, _QWORD, const char *, __int64, int))(*(_QWORD *)v3 + 32LL))(
         v3,
         0,
         "No-Cache",
         8,
         1) >= 0 )
    return 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *))(*a1 + 32))(a1);
  (*(void (__fastcall **)(__int64, __int64, const char *))(*(_QWORD *)v4 + 24LL))(v4, 500, "Server Error");
  return 2;
}

```

## disassembly

```asm
0x180003730  mov     r11, rsp
0x180003733  mov     [r11+18h], rbx
0x180003737  push    rdi
0x180003738  sub     rsp, 40h
0x18000373c  mov     rax, [rcx]
0x18000373f  lea     r9, [r11+8]
0x180003743  lea     r8, [r11+10h]
0x180003747  mov     qword ptr [r11+10h], 0
0x18000374f  lea     rdx, aAppWarmingUp; "APP_WARMING_UP"
0x180003756  mov     [rsp+48h+arg_0], 0
0x18000375e  mov     rbx, rcx
0x180003761  mov     rax, [rax+78h]
0x180003765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000376a  test    eax, eax
0x18000376c  js      loc_180003803
0x180003772  mov     rax, [rsp+48h+arg_8]
0x180003777  cmp     byte ptr [rax], 31h ; '1'
0x18000377a  jnz     loc_180003803
0x180003780  mov     rax, [rbx]
0x180003783  mov     rcx, rbx
0x180003786  mov     rax, [rax+20h]
0x18000378a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000378f  mov     r10, rax
0x180003792  mov     [rsp+48h+var_28], 1
0x18000379a  mov     r9d, 8
0x1800037a0  lea     r8, aNoCache; "No-Cache"
0x1800037a7  xor     edx, edx
0x1800037a9  mov     rcx, [rax]
0x1800037ac  mov     rax, [rcx+20h]
0x1800037b0  mov     rcx, r10
0x1800037b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b8  mov     edi, eax
0x1800037ba  test    eax, eax
0x1800037bc  jns     short loc_180003803
0x1800037be  mov     rcx, [rbx]
0x1800037c1  mov     rax, [rcx+20h]
0x1800037c5  mov     rcx, rbx
0x1800037c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037cd  xor     r9d, r9d
0x1800037d0  lea     r8, aServerError; "Server Error"
0x1800037d7  mov     r10, rax
0x1800037da  mov     [rsp+48h+var_18], r9d
0x1800037df  mov     [rsp+48h+var_20], r9
0x1800037e4  mov     edx, 1F4h
0x1800037e9  mov     rcx, [rax]
0x1800037ec  mov     [rsp+48h+var_28], edi
0x1800037f0  mov     rax, [rcx+18h]
0x1800037f4  mov     rcx, r10
0x1800037f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037fc  mov     eax, 2
0x180003801  jmp     short loc_180003805
0x180003803  xor     eax, eax
0x180003805  mov     rbx, [rsp+48h+arg_10]
0x18000380a  add     rsp, 40h
0x18000380e  pop     rdi
0x18000380f  retn
```

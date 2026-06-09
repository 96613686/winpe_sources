# THREAD_MANAGER::DoThreadParking(void)

- ea: `0x180002bc0`
- end: `0x180002c2e`
- name: `?DoThreadParking@THREAD_MANAGER@@AEAAXXZ`
- size: `110`
- prototype: `void __fastcall(struct _OVERLAPPED *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001450`

## callees

- `0x180001420`
- `0x180002bc0`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180002c0d`
- `iisutil!PuDbgPrint` at `0x180002c0d`

## string_xrefs

- `0x180002c06`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`
- `0x180002bed`: `W3TP: Posting to park a thread\n`
- `0x180002bf4`: `THREAD_MANAGER::DoThreadParking`

## pseudocode

```c
void __fastcall THREAD_MANAGER::DoThreadParking(struct _OVERLAPPED *this)
{
  _DWORD *Pointer; // rcx

  Pointer = this[3].Pointer;
  if ( !Pointer || (signed int)(HIDWORD(this[2].InternalHigh) - this[2].Offset) > Pointer[12] )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
        1426,
        "THREAD_MANAGER::DoThreadParking",
        "W3TP: Posting to park a thread\n");
    THREAD_POOL::PostCompletion(
      (THREAD_POOL *)this[3].InternalHigh,
      0,
      (void (*)(unsigned int, unsigned int, struct _OVERLAPPED *))THREAD_MANAGER::ParkThread,
      this);
  }
}

```

## disassembly

```asm
0x180002bc0  push    rbx
0x180002bc2  sub     rsp, 30h
0x180002bc6  mov     rbx, rcx
0x180002bc9  mov     rcx, [rcx+70h]
0x180002bcd  test    rcx, rcx
0x180002bd0  jz      short loc_180002BDD
0x180002bd2  mov     eax, [rbx+4Ch]
0x180002bd5  sub     eax, [rbx+50h]
0x180002bd8  cmp     eax, [rcx+30h]
0x180002bdb  jle     short loc_180002C28
0x180002bdd  test    cs:g_dwDebugFlags, 3
0x180002be4  jz      short loc_180002C13
0x180002be6  mov     rcx, cs:g_pDebug
0x180002bed  lea     rax, aW3tpPostingToP; "W3TP: Posting to park a thread\n"
0x180002bf4  lea     r9, aThreadManagerD_1; "THREAD_MANAGER::DoThreadParking"
0x180002bfb  mov     [rsp+38h+var_18], rax
0x180002c00  mov     r8d, 592h
0x180002c06  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002c0d  call    cs:__imp_PuDbgPrint
0x180002c13  mov     rcx, [rbx+68h]; this
0x180002c17  lea     r8, ?ParkThread@THREAD_MANAGER@@CAXKKPEAU_OVERLAPPED@@@Z; void (*)(unsigned int, unsigned int, struct _OVERLAPPED *)
0x180002c1e  mov     r9, rbx; struct _OVERLAPPED *
0x180002c21  xor     edx, edx; unsigned int
0x180002c23  call    ?PostCompletion@THREAD_POOL@@QEAAHKP6AXKKPEAU_OVERLAPPED@@@Z0@Z; THREAD_POOL::PostCompletion(ulong,void (*)(ulong,ulong,_OVERLAPPED *),_OVERLAPPED *)
0x180002c28  add     rsp, 30h
0x180002c2c  pop     rbx
0x180002c2d  retn
```

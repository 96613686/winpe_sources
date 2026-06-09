# CThrottler::RemoveItemFromList(CUpdateItem *,int)

- ea: `0x18001afbc`
- end: `0x18001b07c`
- name: `?RemoveItemFromList@CThrottler@@AEAAJPEAUCUpdateItem@@H@Z`
- size: `192`
- prototype: `int(CThrottler *__hidden this, struct CUpdateItem *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x18001b8a0`

## callees

- `0x180019ca4`
- `0x18001a89c`
- `0x18001afbc`
- `0x18001ba40`
- `0x18001bf10`

## import_xrefs

- `WININET!InternetAutodialHangup` at `0x18001b064`
- `WININET!InternetAutodialHangup` at `0x18001b064`

## pseudocode

```c
__int64 __fastcall CThrottler::RemoveItemFromList(CThrottler *this, struct CUpdateItem *a2)
{
  _QWORD *v2; // rdi
  unsigned int v5; // r14d
  __int64 v6; // rbp
  int CookieIndexInQueue; // eax
  __int64 v8; // rcx
  __int64 v9; // r11
  __int64 v10; // rax

  v2 = (_QWORD *)((char *)this + 40);
  v5 = -2147418113;
  if ( a2 )
  {
    v6 = 0;
    CookieIndexInQueue = CThrottler::GetCookieIndexInQueue(this, (const struct _GUID *)((char *)a2 + 8));
    if ( CookieIndexInQueue >= 0 )
      *(_QWORD *)(v8 + 8LL * CookieIndexInQueue + 56) = 0;
    while ( v9 )
    {
      v10 = *(_QWORD *)(v9 + 32);
      if ( (struct CUpdateItem *)v9 == a2 )
      {
        if ( v6 )
          *(_QWORD *)(v6 + 32) = v10;
        else
          *v2 = v10;
        if ( *(struct CUpdateItem **)(v8 + 48) == a2 )
          *(_QWORD *)(v8 + 48) = v6;
        v5 = 0;
        break;
      }
      v6 = v9;
      v9 = *(_QWORD *)(v9 + 32);
    }
    CSyncMgrNode::~CSyncMgrNode(a2);
    operator delete(a2);
  }
  if ( !*v2 )
  {
    if ( __CFSHR__(*((_DWORD *)this + 26), 4) )
    {
LABEL_18:
      SetGlobalOffline(1);
      *((_DWORD *)this + 26) &= 0xFFFFFFE7;
      return v5;
    }
    if ( (*((_BYTE *)this + 104) & 0x10) != 0 )
    {
      if ( !__CFSHR__(*((_DWORD *)this + 26), 4) )
      {
        InternetAutodialHangup(0);
        *((_DWORD *)this + 26) &= ~0x10u;
        return v5;
      }
      goto LABEL_18;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001afbc  push    rbx
0x18001afbe  push    rbp
0x18001afbf  push    rsi
0x18001afc0  push    rdi
0x18001afc1  push    r14
0x18001afc3  sub     rsp, 20h
0x18001afc7  lea     rdi, [rcx+28h]
0x18001afcb  mov     rsi, rdx
0x18001afce  mov     rbx, rcx
0x18001afd1  mov     r14d, 8000FFFFh
0x18001afd7  test    rdx, rdx
0x18001afda  jz      short loc_18001B036
0x18001afdc  mov     r11, [rdi]
0x18001afdf  add     rdx, 8; struct _GUID *
0x18001afe3  xor     ebp, ebp
0x18001afe5  call    ?GetCookieIndexInQueue@CThrottler@@AEAAHPEBU_GUID@@@Z; CThrottler::GetCookieIndexInQueue(_GUID const *)
0x18001afea  test    eax, eax
0x18001afec  js      short loc_18001AFF5
0x18001afee  cdqe
0x18001aff0  mov     [rcx+rax*8+38h], rbp
0x18001aff5  test    r11, r11
0x18001aff8  jz      short loc_18001B026
0x18001affa  mov     rax, [r11+20h]
0x18001affe  cmp     r11, rsi
0x18001b001  jz      short loc_18001B00B
0x18001b003  mov     rbp, r11
0x18001b006  mov     r11, rax
0x18001b009  jmp     short loc_18001AFF5
0x18001b00b  test    rbp, rbp
0x18001b00e  jz      short loc_18001B016
0x18001b010  mov     [rbp+20h], rax
0x18001b014  jmp     short loc_18001B019
0x18001b016  mov     [rdi], rax
0x18001b019  cmp     [rcx+30h], rsi
0x18001b01d  jnz     short loc_18001B023
0x18001b01f  mov     [rcx+30h], rbp
0x18001b023  xor     r14d, r14d
0x18001b026  mov     rcx, rsi; this
0x18001b029  call    ??1CSyncMgrNode@@QEAA@XZ; CSyncMgrNode::~CSyncMgrNode(void)
0x18001b02e  mov     rcx, rsi; lpMem
0x18001b031  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b036  cmp     qword ptr [rdi], 0
0x18001b03a  jnz     short loc_18001B06E
0x18001b03c  mov     eax, [rbx+68h]
0x18001b03f  shr     eax, 4
0x18001b042  sbb     eax, eax
0x18001b044  test    eax, eax
0x18001b046  jnz     short loc_18001B052
0x18001b048  test    byte ptr [rbx+68h], 10h
0x18001b04c  jz      short loc_18001B06E
0x18001b04e  test    eax, eax
0x18001b050  jz      short loc_18001B062
0x18001b052  mov     ecx, 1; int
0x18001b057  call    ?SetGlobalOffline@@YAXH@Z; SetGlobalOffline(int)
0x18001b05c  and     dword ptr [rbx+68h], 0FFFFFFE7h
0x18001b060  jmp     short loc_18001B06E
0x18001b062  xor     ecx, ecx; dwReserved
0x18001b064  call    cs:__imp_InternetAutodialHangup
0x18001b06a  and     dword ptr [rbx+68h], 0FFFFFFEFh
0x18001b06e  mov     eax, r14d
0x18001b071  add     rsp, 20h
0x18001b075  pop     r14
0x18001b077  pop     rdi
0x18001b078  pop     rsi
0x18001b079  pop     rbp
0x18001b07a  pop     rbx
0x18001b07b  retn
```

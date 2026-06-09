# CNotification::Initialize(IXMLDOMNode *,IXMLDOMNode *)

- ea: `0x180002850`
- end: `0x1800028bb`
- name: `?Initialize@CNotification@@QEAAJPEAUIXMLDOMNode@@0@Z`
- size: `107`
- prototype: `__int64 __fastcall(CNotification *__hidden this, struct IXMLDOMNode *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005f60`

## callees

- `0x180002850`
- `0x180002de0`
- `0x180003384`
- `0x18000b13c`

## pseudocode

```c
__int64 __fastcall CNotification::Initialize(struct IXMLDOMNode *this, struct IXMLDOMNode *a2, struct IXMLDOMNode *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // r8d

  v5 = CNotification::SchdpInitializeNotification(this, a2);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 891;
LABEL_6:
    SdpDebugTrace(1u, L"CNotification::Initialize", v7, v5);
    return v6;
  }
  if ( a3 )
  {
    v5 = CNotification::SchdpInitializeParameters((struct IXMLDOMDocument2 *)this, a3);
    v6 = v5;
    if ( v5 < 0 )
    {
      v7 = 895;
      goto LABEL_6;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180002850  mov     [rsp+arg_0], rbx
0x180002855  mov     [rsp+arg_8], rsi
0x18000285a  push    rdi
0x18000285b  sub     rsp, 20h
0x18000285f  mov     rdi, r8
0x180002862  mov     rsi, rcx
0x180002865  call    ?SchdpInitializeNotification@CNotification@@AEAAJPEAUIXMLDOMNode@@@Z; CNotification::SchdpInitializeNotification(IXMLDOMNode *)
0x18000286a  mov     ebx, eax
0x18000286c  test    eax, eax
0x18000286e  jns     short loc_180002878
0x180002870  mov     r8d, 37Bh
0x180002876  jmp     short loc_180002894
0x180002878  test    rdi, rdi
0x18000287b  jz      short loc_1800028A8
0x18000287d  mov     rdx, rdi; struct IXMLDOMNode *
0x180002880  mov     rcx, rsi; this
0x180002883  call    ?SchdpInitializeParameters@CNotification@@AEAAJPEAUIXMLDOMNode@@@Z; CNotification::SchdpInitializeParameters(IXMLDOMNode *)
0x180002888  mov     ebx, eax
0x18000288a  test    eax, eax
0x18000288c  jns     short loc_1800028A8
0x18000288e  mov     r8d, 37Fh; int
0x180002894  mov     r9d, eax; int
0x180002897  lea     rdx, aCnotificationI; "CNotification::Initialize"
0x18000289e  mov     ecx, 1; Level
0x1800028a3  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800028a8  mov     rsi, [rsp+28h+arg_8]
0x1800028ad  mov     eax, ebx
0x1800028af  mov     rbx, [rsp+28h+arg_0]
0x1800028b4  add     rsp, 20h
0x1800028b8  pop     rdi
0x1800028b9  retn
```

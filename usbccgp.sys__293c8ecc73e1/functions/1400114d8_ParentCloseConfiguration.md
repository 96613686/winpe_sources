# ParentCloseConfiguration

- ea: `0x1400114d8`
- end: `0x1400115c1`
- name: `ParentCloseConfiguration`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400124cc`

## callees

- `0x14000a6cc`
- `0x14000b0ec`
- `0x14000b1f0`
- `0x14000b40c`
- `0x1400114d8`

## pseudocode

```c
void __fastcall ParentCloseConfiguration(__int64 a1)
{
  NTSTATUS v2; // eax
  int v3; // r8d
  int v4; // r9d
  _UNKNOWN **v5; // rdx
  int v6; // eax
  _UNKNOWN **v7; // rdx
  PURB Urb; // [rsp+40h] [rbp+8h] BYREF

  Urb = 0;
  v2 = USBD_UrbAllocate(*(USBD_HANDLE *)(a1 + 1344), &Urb);
  if ( v2 >= 0 )
  {
    Urb->UrbHeader.Length = 88;
    Urb->UrbHeader.Function = 0;
    Urb->UrbSelectInterface.ConfigurationHandle = 0;
    v6 = SubmitUrb(a1, (_DWORD)Urb, v3, v4);
    if ( v6 < 0 )
    {
      v7 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1 + 1368),
          (_DWORD)v7,
          8,
          18,
          (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
          v6);
      }
    }
    USBD_UrbFree(*(USBD_HANDLE *)(a1 + 1344), Urb);
  }
  else
  {
    v5 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        (_DWORD)v5,
        8,
        17,
        (__int64)WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids,
        v2);
    }
  }
}

```

## disassembly

```asm
0x1400114d8  push    rbx
0x1400114da  sub     rsp, 30h
0x1400114de  mov     rbx, rcx
0x1400114e1  mov     [rsp+38h+Urb], 0
0x1400114ea  mov     rcx, [rcx+540h]; USBDHandle
0x1400114f1  lea     rdx, [rsp+38h+Urb]; Urb
0x1400114f6  call    USBD_UrbAllocate
0x1400114fb  test    eax, eax
0x1400114fd  jns     short loc_14001153D
0x1400114ff  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140011506  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14001150d  jz      loc_1400115BA
0x140011513  mov     rcx, [rbx+558h]
0x14001151a  mov     r9d, 11h
0x140011520  mov     [rsp+38h+var_10], eax
0x140011524  mov     dl, 2
0x140011526  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14001152d  mov     [rsp+38h+var_18], rax
0x140011532  lea     r8d, [r9-9]
0x140011536  call    WPP_RECORDER_SF_d
0x14001153b  jmp     short loc_1400115BA
0x14001153d  mov     rax, [rsp+38h+Urb]
0x140011542  xor     ecx, ecx
0x140011544  mov     byte ptr [rsp+38h+var_10], 1
0x140011549  mov     word ptr [rax], 58h ; 'X'
0x14001154e  mov     rax, [rsp+38h+Urb]
0x140011553  mov     [rax+2], cx
0x140011557  mov     rax, [rsp+38h+Urb]
0x14001155c  mov     [rax+18h], rcx
0x140011560  mov     rcx, rbx
0x140011563  mov     rdx, [rsp+38h+Urb]
0x140011568  call    SubmitUrb
0x14001156d  test    eax, eax
0x14001156f  jns     short loc_1400115A9
0x140011571  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140011578  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14001157f  jz      short loc_1400115A9
0x140011581  mov     rcx, [rbx+558h]
0x140011588  mov     r9d, 12h
0x14001158e  mov     [rsp+38h+var_10], eax
0x140011592  mov     dl, 2
0x140011594  lea     rax, WPP_67f943e5aefd342b55897d48a43d0d27_Traceguids
0x14001159b  mov     [rsp+38h+var_18], rax
0x1400115a0  lea     r8d, [r9-0Ah]
0x1400115a4  call    WPP_RECORDER_SF_d
0x1400115a9  mov     rdx, [rsp+38h+Urb]; Urb
0x1400115ae  mov     rcx, [rbx+540h]; USBDHandle
0x1400115b5  call    USBD_UrbFree
0x1400115ba  add     rsp, 30h
0x1400115be  pop     rbx
0x1400115bf  retn
```

# CPicturePasswordGestureHelper::Unregister(bool,bool)

- ea: `0x180014938`
- end: `0x1800149de`
- name: `?Unregister@CPicturePasswordGestureHelper@@QEAAX_N0@Z`
- size: `166`
- prototype: `void __fastcall(CPicturePasswordGestureHelper *__hidden this, bool, bool)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e0dc`
- `0x180012d7c`
- `0x180013f60`

## callees

- `0x180010d2c`
- `0x180014938`
- `0x180018a28`

## import_xrefs

- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180014983`
- `DUI70!?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z` at `0x180014983`
- `gdiplus!GdiplusShutdown` at `0x1800149b7`
- `gdiplus!GdiplusShutdown` at `0x1800149b7`

## pseudocode

```c
void __fastcall CPicturePasswordGestureHelper::Unregister(CPicturePasswordGestureHelper *this, char a2)
{
  CPrivateNotificationWindow *v4; // rcx
  DirectUI::Element *v5; // rcx

  if ( *((_DWORD *)this + 8) != 1 )
  {
    v4 = (CPrivateNotificationWindow *)*((_QWORD *)this + 22);
    if ( v4 )
    {
      CPrivateNotificationWindow::Release(v4);
      *((_QWORD *)this + 22) = 0;
    }
    v5 = (DirectUI::Element *)*((_QWORD *)this + 2);
    *((_BYTE *)this + 44) = 0;
    if ( v5 )
    {
      if ( !a2 )
        DirectUI::Element::RemoveListener(v5, this);
      *((_QWORD *)this + 2) = 0;
      *((_QWORD *)this + 3) = 0;
    }
    CTSimpleArray<GESTURE_SIGNATURE,4294967294,CTPolicyCoTaskMem<GESTURE_SIGNATURE>,CSimpleArrayStandardCompareHelper<GESTURE_SIGNATURE>,CSimpleArrayStandardMergeHelper<GESTURE_SIGNATURE>>::RemoveAll((__int64)this + 88);
    CTSimpleArray<GESTURE_SIGNATURE,4294967294,CTPolicyCoTaskMem<GESTURE_SIGNATURE>,CSimpleArrayStandardCompareHelper<GESTURE_SIGNATURE>,CSimpleArrayStandardMergeHelper<GESTURE_SIGNATURE>>::RemoveAll((__int64)this + 128);
    if ( *((_QWORD *)this + 7) )
    {
      GdiplusShutdown();
      *((_QWORD *)this + 7) = 0;
    }
    *((_BYTE *)this + 188) = 0;
    *((_DWORD *)this + 8) = 1;
  }
}

```

## disassembly

```asm
0x180014938  mov     [rsp+arg_0], rbx
0x18001493d  push    rdi
0x18001493e  sub     rsp, 20h
0x180014942  cmp     dword ptr [rcx+20h], 1
0x180014946  mov     dil, dl
0x180014949  mov     rbx, rcx
0x18001494c  jz      loc_1800149D3
0x180014952  mov     rcx, [rcx+0B0h]; this
0x180014959  test    rcx, rcx
0x18001495c  jz      short loc_18001496E
0x18001495e  call    ?Release@CPrivateNotificationWindow@@QEAAKXZ; CPrivateNotificationWindow::Release(void)
0x180014963  mov     qword ptr [rbx+0B0h], 0
0x18001496e  mov     rcx, [rbx+10h]
0x180014972  mov     byte ptr [rbx+2Ch], 0
0x180014976  test    rcx, rcx
0x180014979  jz      short loc_180014999
0x18001497b  test    dil, dil
0x18001497e  jnz     short loc_180014989
0x180014980  mov     rdx, rbx
0x180014983  call    cs:__imp_?RemoveListener@Element@DirectUI@@QEAAXPEAUIElementListener@2@@Z; DirectUI::Element::RemoveListener(DirectUI::IElementListener *)
0x180014989  mov     qword ptr [rbx+10h], 0
0x180014991  mov     qword ptr [rbx+18h], 0
0x180014999  lea     rcx, [rbx+58h]
0x18001499d  call    ?RemoveAll@?$CTSimpleArray@UGESTURE_SIGNATURE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UGESTURE_SIGNATURE@@@@V?$CSimpleArrayStandardCompareHelper@UGESTURE_SIGNATURE@@@@V?$CSimpleArrayStandardMergeHelper@UGESTURE_SIGNATURE@@@@@@QEAAXXZ; CTSimpleArray<GESTURE_SIGNATURE,4294967294,CTPolicyCoTaskMem<GESTURE_SIGNATURE>,CSimpleArrayStandardCompareHelper<GESTURE_SIGNATURE>,CSimpleArrayStandardMergeHelper<GESTURE_SIGNATURE>>::RemoveAll(void)
0x1800149a2  lea     rcx, [rbx+80h]
0x1800149a9  call    ?RemoveAll@?$CTSimpleArray@UGESTURE_SIGNATURE@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UGESTURE_SIGNATURE@@@@V?$CSimpleArrayStandardCompareHelper@UGESTURE_SIGNATURE@@@@V?$CSimpleArrayStandardMergeHelper@UGESTURE_SIGNATURE@@@@@@QEAAXXZ; CTSimpleArray<GESTURE_SIGNATURE,4294967294,CTPolicyCoTaskMem<GESTURE_SIGNATURE>,CSimpleArrayStandardCompareHelper<GESTURE_SIGNATURE>,CSimpleArrayStandardMergeHelper<GESTURE_SIGNATURE>>::RemoveAll(void)
0x1800149ae  mov     rcx, [rbx+38h]
0x1800149b2  test    rcx, rcx
0x1800149b5  jz      short loc_1800149C5
0x1800149b7  call    cs:__imp_GdiplusShutdown
0x1800149bd  mov     qword ptr [rbx+38h], 0
0x1800149c5  mov     byte ptr [rbx+0BCh], 0
0x1800149cc  mov     dword ptr [rbx+20h], 1
0x1800149d3  mov     rbx, [rsp+28h+arg_0]
0x1800149d8  add     rsp, 20h
0x1800149dc  pop     rdi
0x1800149dd  retn
```

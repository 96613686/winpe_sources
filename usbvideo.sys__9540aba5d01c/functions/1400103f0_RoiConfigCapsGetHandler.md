# RoiConfigCapsGetHandler

- ea: `0x1400103f0`
- end: `0x1400104dd`
- name: `RoiConfigCapsGetHandler`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x1400103f0`
- `0x14001b118`
- `0x140040b40`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x140010400`
- `ks!KsGetFilterFromIrp` at `0x140010400`

## pseudocode

```c
__int64 __fastcall RoiConfigCapsGetHandler(IRP *a1, __int64 a2, _DWORD *a3)
{
  PKSFILTER FilterFromIrp; // rax
  _DWORD *v6; // r14
  unsigned int Length; // edx
  ULONG_PTR v8; // rcx
  unsigned int v9; // ebx

  FilterFromIrp = KsGetFilterFromIrp(a1);
  if ( FilterFromIrp )
  {
    v6 = *(_DWORD **)&(*(const KSAUTOMATION_TABLE **)((char *)&FilterFromIrp->Descriptor->NodeDescriptors[9].AutomationTable
                                                    + FilterFromIrp->Descriptor->NodeDescriptorSize
                                                    * *((_DWORD *)FilterFromIrp->Context + 10)))[1].EventSetsCount;
    Length = a1->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
    v8 = (unsigned int)v6[2];
    if ( Length )
    {
      if ( Length >= (unsigned int)v8 )
      {
        if ( a3 && *a3 == *v6 && a3[1] == v6[1] && a3[2] >= (unsigned int)v8 )
        {
          v9 = 0;
          memmove(a3, v6, (unsigned int)v6[2]);
          a1->IoStatus.Information = (unsigned int)v6[2];
        }
        else
        {
          v9 = -1073741811;
        }
      }
      else
      {
        v9 = -1073741789;
      }
    }
    else
    {
      a1->IoStatus.Information = v8;
      v9 = -2147483643;
    }
  }
  else
  {
    v9 = -1073741823;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_ebeb762af7253cd886177c9038d34848_Traceguids, v9);
  a1->IoStatus.Status = v9;
  return v9;
}

```

## disassembly

```asm
0x1400103f0  push    rbx
0x1400103f2  push    rsi
0x1400103f3  push    rdi
0x1400103f4  push    r14
0x1400103f6  sub     rsp, 28h
0x1400103fa  mov     rdi, r8
0x1400103fd  mov     rsi, rcx
0x140010400  call    cs:__imp_KsGetFilterFromIrp
0x140010407  nop     dword ptr [rax+rax+00h]
0x14001040c  test    rax, rax
0x14001040f  jz      loc_140010497
0x140010415  mov     r9, [rax]
0x140010418  mov     rax, [rax+10h]
0x14001041c  mov     edx, [rax+28h]
0x14001041f  imul    edx, [r9+44h]
0x140010424  mov     rax, [r9+48h]
0x140010428  mov     rcx, [rdx+rax+0D8h]
0x140010430  mov     rax, [rsi+0B8h]
0x140010437  mov     r14, [rcx+50h]
0x14001043b  mov     edx, [rax+8]
0x14001043e  mov     ecx, [r14+8]
0x140010442  test    edx, edx
0x140010444  jnz     short loc_140010451
0x140010446  mov     [rsi+38h], rcx
0x14001044a  mov     ebx, 80000005h
0x14001044f  jmp     short loc_14001049C
0x140010451  cmp     edx, ecx
0x140010453  jnb     short loc_14001045C
0x140010455  mov     ebx, 0C0000023h
0x14001045a  jmp     short loc_14001049C
0x14001045c  test    rdi, rdi
0x14001045f  jnz     short loc_140010468
0x140010461  mov     ebx, 0C000000Dh
0x140010466  jmp     short loc_14001049C
0x140010468  mov     eax, [r14]
0x14001046b  cmp     [rdi], eax
0x14001046d  jnz     short loc_140010461
0x14001046f  mov     eax, [r14+4]
0x140010473  cmp     [rdi+4], eax
0x140010476  jnz     short loc_140010461
0x140010478  cmp     [rdi+8], ecx
0x14001047b  jb      short loc_140010461
0x14001047d  mov     r8, rcx; Size
0x140010480  xor     ebx, ebx
0x140010482  mov     rcx, rdi; void *
0x140010485  mov     rdx, r14; Src
0x140010488  call    memmove
0x14001048d  mov     eax, [r14+8]
0x140010491  mov     [rsi+38h], rax
0x140010495  jmp     short loc_14001049C
0x140010497  mov     ebx, 0C0000001h
0x14001049c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400104a3  lea     rax, WPP_GLOBAL_Control
0x1400104aa  cmp     rcx, rax
0x1400104ad  jz      short loc_1400104CD
0x1400104af  cmp     byte ptr [rcx+29h], 4
0x1400104b3  jb      short loc_1400104CD
0x1400104b5  mov     rcx, [rcx+18h]
0x1400104b9  lea     r8, WPP_ebeb762af7253cd886177c9038d34848_Traceguids
0x1400104c0  mov     edx, 11h
0x1400104c5  mov     r9d, ebx
0x1400104c8  call    WPP_SF_d
0x1400104cd  mov     [rsi+30h], ebx
0x1400104d0  mov     eax, ebx
0x1400104d2  add     rsp, 28h
0x1400104d6  pop     r14
0x1400104d8  pop     rdi
0x1400104d9  pop     rsi
0x1400104da  pop     rbx
0x1400104db  retn
```

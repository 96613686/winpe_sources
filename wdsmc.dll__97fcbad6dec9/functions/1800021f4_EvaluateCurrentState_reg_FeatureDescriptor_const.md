# EvaluateCurrentState(reg_FeatureDescriptor const *)

- ea: `0x1800021f4`
- end: `0x18000221a`
- name: `?EvaluateCurrentState@@YAHPEBUreg_FeatureDescriptor@@@Z`
- size: `38`
- prototype: `__int64 __fastcall(const struct reg_FeatureDescriptor *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002c70`

## callees

- `0x1800020bc`
- `0x1800021f4`

## pseudocode

```c
char __fastcall EvaluateCurrentState(const struct reg_FeatureDescriptor *a1)
{
  if ( *(_DWORD *)g_Feature_4017186106_50692837_FeatureDescriptorDetails )
    return *(_DWORD *)g_Feature_4017186106_50692837_FeatureDescriptorDetails != 1;
  else
    return EvaluateCurrentStateFromRegistry(
             50692837,
             2,
             (volatile signed __int32 *)g_Feature_4017186106_50692837_FeatureDescriptorDetails);
}

```

## disassembly

```asm
0x1800021f4  mov     r8, cs:g_Feature_4017186106_50692837_FeatureDescriptorDetails
0x1800021fb  xor     eax, eax
0x1800021fd  mov     ecx, [r8]
0x180002200  test    ecx, ecx
0x180002202  jz      short loc_18000220B
0x180002204  cmp     ecx, 1
0x180002207  setnz   al
0x18000220a  retn
0x18000220b  mov     edx, 2
0x180002210  mov     ecx, 30582E5h
0x180002215  jmp     ?EvaluateCurrentStateFromRegistry@@YAHIW4reg_FeatureStage@@PECJ@Z; EvaluateCurrentStateFromRegistry(uint,reg_FeatureStage,long volatile *)
```
